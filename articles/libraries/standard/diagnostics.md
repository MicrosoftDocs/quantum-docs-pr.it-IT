---
title: 'Q # librerie standard-diagnostica | Microsoft Docs'
description: 'Librerie standard Q #-diagnostica'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: b59f91b660281167eab182529b415b6d379e3d63
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184492"
---
# <a name="diagnostics"></a>Diagnostica #

Come per lo sviluppo classico, è importante essere in grado di diagnosticare errori ed errori nei programmi Quantum.
Le librerie standard Q # forniscono una serie di modi diversi per garantire la correttezza dei programmi Quantum, come descritto in <xref:microsoft.quantum.techniques.testing-and-debugging>.
In gran parte, questo supporto viene fornito sotto forma di funzioni e operazioni che indicano al computer di destinazione di fornire informazioni di diagnostica aggiuntive al programma o allo sviluppatore host oppure di applicare la correttezza delle condizioni e delle invarianti espresse tramite la funzione o la chiamata dell'operazione.

## <a name="machine-diagnostics"></a>Diagnostica del computer ##

La diagnostica sui valori classici può essere ottenuta usando la funzione <xref:microsoft.quantum.intrinsic.message> per registrare un messaggio in modo dipendente dal computer.
Per impostazione predefinita, la stringa viene scritta nella console.
Utilizzato insieme alle stringhe interpolate, <xref:microsoft.quantum.intrinsic.message> semplifica la segnalazione di informazioni di diagnostica sui valori classici:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` dispone di `(String -> Unit)`di firma, che rappresenta di nuovo che la creazione di un messaggio di log di debug non può essere osservata dall'interno di Q #.

Il <xref:microsoft.quantum.diagnostics.dumpmachine> e <xref:microsoft.quantum.diagnostics.dumpregister> chiamabili indica ai computer di destinazione di fornire informazioni di diagnostica su tutti i qubits attualmente allocati o su un registro specifico di qubits, rispettivamente.
Ogni computer di destinazione varia in base alle informazioni di diagnostica fornite in risposta a un'istruzione di dump.
Il computer di destinazione del [simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator) , ad esempio, fornisce il programma host con il vettore di stato usato internamente per rappresentare un registro di qubits.
Per confronto, il computer di destinazione del [simulatore Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) fornisce un solo bit classico per ogni qubit.

 Per altre informazioni sull'output del `DumpMachine` del [simulatore di stato completo](xref:microsoft.quantum.machines.full-state-simulator) , vedere la sezione funzioni dump dell' [articolo test e debug](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions).


## <a name="facts-and-assertions"></a>Fact e asserzioni ##

Come illustrato in [test e debug](xref:microsoft.quantum.techniques.testing-and-debugging), una funzione o un'operazione con firma `Unit -> Unit` o `Unit => Unit`, rispettivamente, può essere chiamata come *unit test*.
Ogni unit test in genere è costituito da un piccolo programma Quantum, insieme a una o più condizioni che verificano la correttezza del programma.
Queste condizioni possono essere disponibili sotto forma di _Fact_, che controllano i valori degli input, o _asserzioni_, che controllano gli Stati di uno o più qubits passati come input.

Ad esempio, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` rappresenta il fatto matematico che $1 + 1 = $2, mentre `AssertQubit(One, qubit)` rappresenta la condizione che la misurazione `qubit` restituirà un `One` con certezza.
Nel primo caso, è possibile verificare la correttezza della condizione data solo i relativi valori, mentre nel secondo caso è necessario conoscere lo stato di qubit per valutare l'asserzione.

Le librerie standard Q # forniscono diverse funzioni per rappresentare i fatti, tra cui:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfact>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Test di stati qubit ###

In pratica, le asserzioni si basano sul fatto che le simulazioni classiche dei meccanici quantistici non devono rispettare il [teorema di non clonazione](https://arxiv.org/abs/quant-ph/9607018), in modo da poter effettuare misurazioni e asserzioni non fisiche quando si usa un simulatore per il computer di destinazione.
Possiamo quindi testare singole operazioni su un simulatore classico prima di distribuirle su hardware.
Nei computer di destinazione che non consentono la valutazione delle asserzioni, le chiamate a <xref:microsoft.quantum.intrinsic.assert> possono essere tranquillamente ignorate.

Più in generale, l'operazione <xref:microsoft.quantum.intrinsic.assert> asserisce che la misurazione del qubits specificato nella base di Pauli specificata avrà sempre il risultato specificato.
Se l'asserzione ha esito negativo, l'esecuzione termina chiamando `fail` con il messaggio specificato.
Per impostazione predefinita, questa operazione non è implementata; i simulatori che possono supportarlo devono fornire un'implementazione che esegua il controllo del runtime.
`Assert` ha `((Pauli[], Qubit[], Result, String) -> ())`di firma.
Poiché `Assert` è una funzione con una tupla vuota come tipo di output, nessun effetto della chiamata `Assert` è osservabile all'interno di un programma Q #.

La funzione <xref:microsoft.quantum.intrinsic.assertprob> Operation asserisce che la misurazione del qubits specificato nella base di Pauli specificata avrà il risultato specificato con la probabilità specificata, entro una certa tolleranza.
La tolleranza è additiva (ad esempio `abs(expected-actual) < tol`).
Se l'asserzione ha esito negativo, l'esecuzione termina chiamando `fail` con il messaggio specificato.
Per impostazione predefinita, questa operazione non è implementata; i simulatori che possono supportarlo devono fornire un'implementazione che esegua il controllo del runtime.
`AssertProb` ha `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`di firma. Il primo dei parametri di `Double` fornisce la probabilità desiderata del risultato e la seconda la tolleranza.

È possibile eseguire altre operazioni oltre ad asserire una sola misurazione, usando il fatto che le informazioni classiche usate da un simulatore per rappresentare lo stato interno di un qubit sono suscettibili alla copia, in modo che non sia necessario eseguire effettivamente una misurazione per testare l'asserzione.
In particolare, ciò consente di ragionare su misurazioni *incompatibili* che non sarebbero possibili sull'hardware effettivo.

Si supponga che `P : Qubit => Unit` sia un'operazione progettata per preparare lo stato $ \ket{\psi} $ quando il relativo input è nello stato $ \ket{0}$.
Let $ \ket{\psi '} $ è lo stato effettivo preparato da `P`.
Quindi, $ \ket{\psi} = \ket{\psi '} $ If e solo se la misurazione di $ \ket{\psi '} $ nell'asse descritto da $ \ket{\psi} $ restituisce sempre `Zero`.
Ovvero \begin{align} \ket{\psi} = \ket{\psi '} \Text{if e only if} \braket{\psi | \psi '} = 1.
\end{align} usando le operazioni primitive definite nel preludio, è possibile eseguire direttamente una misurazione che restituisce `Zero` se $ \ket{\psi} $ è un autostato di uno degli operatori di Pauli.


L'operazione <xref:microsoft.quantum.diagnostics.assertqubit> fornisce un'abbreviazione particolarmente utile nel caso in cui si desideri testare l'asserzione $ \ket{\psi} = \ket{0}$.
Si tratta di un'operazione comune, ad esempio, quando è stato non calcolato per restituire ancilla qubits a $ \ket{0}$ prima di rilasciarli.
L'asserzione di $ \ket{0}$ è utile anche quando si desidera dichiarare che due operazioni di preparazione dello stato `P` e `Q` preparano lo stesso stato e quando `Q` supporta `Adjoint`.
In particolare,

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

In generale, tuttavia, potrebbe non essere possibile accedere alle asserzioni relative agli Stati che non coincidono con autostati degli operatori di Pauli.
Ad esempio, $ \ket{\psi} = (\ket{0} + e ^ {i \Pi/8} \ket{1})/\sqrt{2}$ non è un autostato di alcun operatore Pauli, in modo da non poter usare <xref:microsoft.quantum.intrinsic.assertprob> per determinare in modo univoco che uno stato $ \ket{\psi '} $ sia uguale a $ \ket{\psi} $.
È invece necessario scomporre l'asserzione $ \ket{\psi '} = \ket{\psi} $ in presupposti che possano essere testati direttamente usando le primitive supportate dal simulatore.
A tale scopo, fare in modo che $ \ket{\psi} = \Alpha \ket{0} + \beta \ket{1}$ per i numeri complessi $ \Alpha = a\_r + a\_i $ e $ \beta $.
Si noti che questa espressione richiede quattro numeri reali $\{un\_r, un\_i, b\_r, b\_i\}$ da specificare, perché ogni numero complesso può essere espresso come la somma di una parte reale e immaginaria.
A causa della fase globale, tuttavia, è possibile scegliere $a\_i = $0, in modo che siano necessari solo tre numeri reali per specificare in modo univoco un solo stato di qubit.

Pertanto, è necessario specificare tre asserzioni indipendenti l'una dall'altra per poter dichiarare lo stato previsto.
A tale scopo, è possibile trovare la probabilità di osservare `Zero` per ogni misurazione di Pauli data $ \Alpha $ e $ \beta $ e di dichiarare ogni indipendentemente.
$X $, $y $ e $z $ be `Result` values rispettivamente per Pauli $X $, $Y $ e $Z $ measurements.
Quindi, usando la funzione di probabilità per Quantum Measurements, \begin{align} \Pr (x = \texttt{Zero} | \Alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr (y = \texttt{Zero} | \Alpha , \beta) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \Pr (z = \texttt{Zero} | \Alpha, \beta) & = \frac12\left (1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_i ^ 2 \right).
\end{align}

L'operazione <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> implementa queste asserzioni date le rappresentazioni di $ \Alpha $ e $ \beta $ come valori di tipo <xref:microsoft.quantum.math.complex>.
Questa operazione è utile quando lo stato previsto può essere calcolato matematicamente.

### <a name="asserting-equality-of-quantum-operations"></a>Asserzione di uguaglianza di operazioni Quantum ###

Fino ad ora, ci siamo preoccupati per le operazioni di test mirate a preparare determinati stati.
Spesso, tuttavia, è interessante il modo in cui un'operazione agisce per gli input arbitrari anziché per un singolo input fisso.
Si supponga, ad esempio, che sia stata implementata un'operazione `U : ((Double, Qubit[]) => () : Adjoint)` corrispondente a una famiglia di operatori unitari $U (t) $ e che sia stato fornito un blocco di `adjoint` esplicito anziché utilizzare `adjoint auto`.
Potrebbe essere interessante affermare che $U ^ \dagger (t) = U (-t) $, come previsto se $t $ rappresenta un tempo di evoluzione.

In generale, esistono due strategie diverse che è possibile seguire per rendere l'asserzione che due operazioni `U` e `V` agiscono in modo identico.
In primo luogo, è possibile verificare che `U(target); (Adjoint V)(target);` manservi ogni stato in una determinata base.
In secondo luogo, è possibile verificare che il `U(target); (Adjoint V)(target);` che agisce sulla metà di uno stato incastrato conserva il groviglio.
Queste strategie sono implementate rispettivamente dalle operazioni canoniche <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> e <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>.

> [!NOTE]
> L'asserzione a cui si fa riferimento descritta sopra funziona in base a [Choi-Jamiłkowski isomorfismo](https://en.wikipedia.org/wiki/Channel-state_duality), un framework matematico che mette in relazione le operazioni su $n $ qubits a stati aggrovigliati in $2n $ qubits.
> In particolare, l'operazione di identità in $n $ qubits è rappresentata da $n $ copie dello stato di $ \ket{\beta_{00}} \mathrel{: =} (\ket{00} + \ket{11})/\sqrt{2}$.
> L'operazione <xref:microsoft.quantum.preparation.preparechoistate> implementa questo isomorfismo, preparando uno stato che rappresenta una determinata operazione.

Approssimativamente, queste strategie si distinguono da un compromesso di spazio-tempo.
L'iterazione di ogni stato di input richiede ulteriore tempo, mentre l'uso di un riferimento richiede l'archiviazione di qubits aggiuntivi.
Nei casi in cui un'operazione implementa un'operazione classica reversibile, in modo che sia interessato solo al suo comportamento sugli stati di base computazionale, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> verifica l'uguaglianza su questo set limitato di input.

> [!TIP]
> L'iterazione sugli stati di input viene gestita dalle operazioni di enumerazione <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> e <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.
> Queste operazioni sono utili più in generale per l'applicazione di un'operazione a ogni elemento del prodotto cartesiano tra due o più set.

In modo più critico, tuttavia, i due approcci verificano diverse proprietà delle operazioni sottoposte a verifica.
Poiché l'asserzione sul posto chiama ogni operazione più volte, una volta per ogni stato di input, eventuali scelte casuali e risultati di misurazione potrebbero cambiare tra le chiamate.
Al contrario, l'asserzione a cui si fa riferimento chiama ogni operazione una sola volta, in modo da verificare che le operazioni siano uguali *in un singolo colpo*.
Entrambi questi test sono utili per garantire la correttezza dei programmi Quantum.


## <a name="further-reading"></a>Altre informazioni ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
