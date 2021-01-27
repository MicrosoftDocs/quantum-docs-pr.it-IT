---
title: Operazioni e funzioni intrinseche in QDK
description: Informazioni sulle funzioni e le funzioni intrinseche in QDK, incluse le funzioni classiche e le operazioni Unity, di rotazione e di misurazione.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6ed5b1677a204b9425f229a3ea0855bb789f3f75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857195"
---
# <a name="the-prelude"></a>Preludio #

Il Q# compilatore e i computer di destinazione inclusi in Quantum Development Kit forniscono un set di funzioni intrinseche e operazioni che possono essere usate durante la scrittura di programmi Quantum in Q# .

## <a name="intrinsic-operations-and-functions"></a>Operazioni e funzioni intrinseche ##

Le operazioni intrinseche definite nella libreria standard rientrano approssimativamente in una delle categorie seguenti:

- Funzioni classiche essenziali, raccolte nello <xref:Microsoft.Quantum.Core> spazio dei nomi.
- Operazioni che rappresentano unitaries composte da [Clifford e $T $ Gates](xref:microsoft.quantum.concepts.qubit).
- Operazioni che rappresentano le rotazioni relative a vari operatori.
- Operazioni di implementazione delle misure.

Dato che il set di Gate di Clifford + $T $ è [universale](xref:microsoft.quantum.concepts.multiple-qubits) per quantum computing, queste operazioni sono sufficienti per implementare qualsiasi algoritmo Quantum in un errore trascurabile di piccole dimensioni.
Fornendo anche le rotazioni, Q# consente al programmatore di lavorare all'interno della singola libreria qubit Unity e CNOT Gate. Questa libreria è molto più semplice da considerare perché non richiede al programmatore di esprimere direttamente la decomposizione di Clifford + $T $ e perché esistono metodi estremamente efficienti per la compilazione di singoli qubit unitaries in Clifford e $T $ Gates (vedere [qui](xref:microsoft.quantum.more-information) per altre informazioni).

Laddove possibile, le operazioni definite nel preludio che agiscono su qubits consentono di applicare la `Controlled` variante, in modo che il computer di destinazione esegua la scomposizione appropriata.

Molte funzioni e operazioni definite in questa parte del preludio sono nello @"microsoft.quantum.intrinsic" spazio dei nomi, in modo che la maggior parte dei Q# file di origine disponga di una `open Microsoft.Quantum.Intrinsic;` direttiva che segue immediatamente la dichiarazione dello spazio dei nomi iniziale.
Lo <xref:Microsoft.Quantum.Core> spazio dei nomi viene aperto automaticamente, in modo che funzioni come <xref:Microsoft.Quantum.Core.Length> possono essere usate senza un' `open` istruzione.

### <a name="common-single-qubit-unitary-operations"></a>Operazioni comuni di Single-Qubit Unity ###

Il preludio definisce anche molte [operazioni comuni a qubit singola](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).
Tutte queste operazioni consentono sia `Controlled` a che a `Adjoint` funtori.

#### <a name="pauli-operators"></a>Operatori Pauli ####

L' <xref:Microsoft.Quantum.Intrinsic.X> operazione implementa l'operatore Pauli $X $.
Questa operazione è talvolta nota anche come controllo `NOT` .
Dispone della firma `(Qubit => Unit is Adj + Ctl)` .
Corrisponde al gruppo qubit singolo:

\begin{Equation} \begin{Bmatrix} 0 & 1 \\ \\ % FIXME: attualmente usa il quadwhack hack.
1 & 0 \end{Bmatrix} \end{Equation}

L' <xref:Microsoft.Quantum.Intrinsic.Y> operazione implementa l'operatore Pauli $Y $.
Dispone della firma `(Qubit => Unit is Adj + Ctl)` .
Corrisponde al gruppo qubit singolo:

\begin{Equation} \begin{Bmatrix} 0 &-i \\ \\ % FIXME: attualmente usa il quadwhack hack.
i & 0 \end{Bmatrix} \end{Equation}

L' <xref:Microsoft.Quantum.Intrinsic.Z> operazione implementa l'operatore Pauli $Z $.
Dispone della firma `(Qubit => Unit is Adj + Ctl)` .
Corrisponde al gruppo qubit singolo:

\begin{Equation} \begin{Bmatrix} 1 & 0 \\ \\ % FIXME: attualmente usa il quadwhack hack.
0 &-1 \end{Bmatrix} \end{Equation}

Di seguito sono riportate le trasformazioni di cui è stato eseguito il mapping alla [sfera Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (l'asse di rotazione in ogni case è evidenziato in rosso):

![Operazioni di Pauli mappate nella sfera Bloch](~/media/prelude_pauliBloch.png)

È importante notare che l'applicazione dello stesso controllo Pauli due volte allo stesso qubit Annulla l'operazione (poiché a questo punto è stata eseguita una rotazione completa di 2 π (360 °) sulla superficie di Bloch, in modo da tornare al punto di partenza. Viene visualizzata la seguente identità:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Questo può essere visualizzato nella sfera Bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Altri Single-Qubit Cliffords ####

L' <xref:Microsoft.Quantum.Intrinsic.H> operazione implementa il controllo Hadamard.
Questo scambia gli assi Pauli $X $ e $Z $ della qubit di destinazione, in modo che $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ e $H \ket{+} = \ket {0} $.
Ha la firma `(Qubit => Unit is Adj + Ctl)` e corrisponde all'unità qubit singolo:

\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % FIXME: attualmente usa la quadwhack hack.
1 &-1 \end{Bmatrix} \end{Equation}

Il controllo Hadamard è particolarmente importante perché può essere usato per creare una superposizione degli Stati $ \ket {0} $ e $ \ket {1} $. Nella rappresentazione di Sphere di Bloch, è più facile pensare a questo come una rotazione di $ \ket{\psi} $ attorno all'asse x di $ \Pi $ radianti ($ 180 ^ \circ $) seguita da una rotazione (in senso orario) intorno all'asse y di $ \ PI/2 $ radianti ($ 90 ^ \circ $):

![Operazione Hadamard mappata nella sfera Bloch](~/media/prelude_hadamardBloch.png)

L' <xref:Microsoft.Quantum.Intrinsic.S> operazione implementa la fase gate $S $.
Si tratta della radice quadrata della matrice dell'operazione Pauli $Z $.
Ovvero $S ^ 2 = Z $.
Ha la firma `(Qubit => Unit is Adj + Ctl)` e corrisponde all'unità qubit singolo:

\begin{Equation} \begin{Bmatrix} 1 & 0 \\ \\ % FIXME: attualmente usa il quadwhack hack.
0 & \end{Bmatrix} \end{Equation}

#### <a name="rotations"></a>Rotazioni ####

Oltre alle operazioni di Pauli e Clifford precedenti, il Q# preludio offre un'ampia gamma di modi per esprimere le rotazioni.
Come descritto in [operazioni Single-qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), la possibilità di ruotare è fondamentale per gli algoritmi Quantum.

Si inizia richiamando che è possibile esprimere qualsiasi operazione Single-qubit usando il $H $ e $T $ Gates, dove $H $ è l'operazione Hadamard e dove \begin{Equation} T \mathrel{: =} \begin{Bmatrix} 1 & 0 \\ \\ % FIXME: attualmente usa il quad back Whack hack.
0 & e ^ {i \Pi/4} \end{Bmatrix} \end{Equation} questa è la radice quadrata dell' <xref:Microsoft.Quantum.Intrinsic.S> operazione, in modo che $T ^ 2 = S $.
Il $T $ Gate viene a sua volta implementato dall' <xref:Microsoft.Quantum.Intrinsic.T> operazione e ha la firma `(Qubit => Unit is Adj + Ctl)` , a indicare che si tratta di un'operazione unitaria su un singolo qubit.

Anche se questo è fondamentalmente sufficiente per descrivere qualsiasi operazione arbitraria a singolo qubit, i computer di destinazione diversi possono avere rappresentazioni più efficienti per le rotazioni sugli operatori di Pauli, in modo che il preludio includa diversi modi per convienently esprimere tali rotazioni.
Il più semplice di questi è l' <xref:Microsoft.Quantum.Intrinsic.R> operazione, che implementa una rotazione intorno a un asse di Pauli specificato, \Begin{Equation} R (\sigma, \Phi) \mathrel{: =} \exp (-i \Phi \sigma/2), \end{Equation} dove $ \sigma $ è un operatore Pauli, $ \Phi $ è un angolo e dove $ \exp $ rappresenta la matrice esponenziale.
Dispone della firma `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , in cui le prime due parti dell'input rappresentano gli argomenti classici $ \sigma $ e $ \Phi $ necessari per specificare l'operatore unitario $R (\sigma, \Phi) $.
È possibile applicare parzialmente $ \sigma $ e $ \Phi $ per ottenere un'operazione il cui tipo è quello di un singolo unità qubit.
Ad esempio, `R(PauliZ, PI() / 4, _)` è di tipo `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> L' <xref:Microsoft.Quantum.Intrinsic.R> operazione divide l'angolo di input di 2 e la moltiplica per-1.
> Per $Z $ rotations, significa che $ \ket {0} $ autostato è ruotato da $-\Phi/$2 e $ \ket {1} $ autostato viene ruotato da $ \phi/$2, in modo che $ \ket {1} $ autostato venga ruotato di $ \Phi $ relativo a $ \ket $ autostato {0} .
>
> In particolare, ciò significa che `T` e `R(PauliZ, PI() / 8, _)` differiscono solo per una [fase globale](xref:microsoft.quantum.glossary#global-phase)irrilevante.
> Per questo motivo, $T $ è talvolta noto come $ \frac{\Pi} {8} $-Gate.
>
> Si noti anche che la rotazione intorno `PauliI` a applica semplicemente una fase globale di $ \Phi/$2. Sebbene tali fasi siano irrilevanti, come affermato nei [documenti concettuali](xref:microsoft.quantum.concepts.qubit), sono rilevanti per le `PauliI` rotazioni controllate.

Negli algoritmi quantistici è spesso utile esprimere le rotazioni come frazioni diadico, in modo che $ \Phi = \Pi k/2 ^ n $ per alcuni $k \in \mathbb{Z} $ e $n \in \mathbb{N} $.
L' <xref:Microsoft.Quantum.Intrinsic.RFrac> operazione implementa una rotazione intorno a un asse di Pauli specificato utilizzando questa convenzione.
Si differenzia da <xref:Microsoft.Quantum.Intrinsic.R> in quanto l'angolo di rotazione viene specificato come due input di tipo `Int` , interpretato come una frazione diadico.
Dispone pertanto della `RFrac` firma `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .
Implementa il singolo qubit Unity $ \exp (i \Pi k \sigma/2 ^ n) $, dove $ \sigma $ è la matrice di Pauli corrispondente al primo argomento, $k $ è il secondo argomento e $n $ è il terzo argomento.
`RFrac(_,k,n,_)` è uguale a. si `R(_,-πk/2^n,_)` noti che l'angolo è il *negativo* della frazione.

L' <xref:Microsoft.Quantum.Intrinsic.Rx> operazione implementa una rotazione intorno all'asse di Pauli $X $.
Dispone della firma `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rx(_, _)` è uguale a `R(PauliX, _, _)`.

L' <xref:Microsoft.Quantum.Intrinsic.Ry> operazione implementa una rotazione intorno all'asse di Pauli $Y $.
Dispone della firma `((Double, Qubit) => Unit is Adj + Ctl)` .
`Ry(_, _)` è uguale a `R(PauliY,_ , _)`.

L' <xref:Microsoft.Quantum.Intrinsic.Rz> operazione implementa una rotazione intorno all'asse di Pauli $Z $.
Dispone della firma `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rz(_, _)` è uguale a `R(PauliZ, _, _)`.

L' <xref:Microsoft.Quantum.Intrinsic.R1> operazione implementa una rotazione in base alla quantità specificata circa $ \ket {1} $, il autostato $-$1 di $Z $.
Dispone della firma `((Double, Qubit) => Unit is Adj + Ctl)` .
`R1(phi,_)` è uguale a `R(PauliZ,phi,_)` seguito da `R(PauliI,-phi,_)` .

L' <xref:Microsoft.Quantum.Intrinsic.R1Frac> operazione implementa una rotazione frazionaria in base alla quantità specificata intorno alla Z = 1 autostato.
Dispone della firma `((Int,Int, Qubit) => Unit is Adj + Ctl)` .
`R1Frac(k,n,_)` è uguale a `RFrac(PauliZ,-k.n+1,_)` seguito da `RFrac(PauliI,k,n+1,_)` .

Di seguito è riportato un esempio di un'operazione di rotazione (intorno all'asse Pauli $Z $, in questa istanza) mappato alla sfera Bloch:

![Operazione di rotazione mappata nella sfera Bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operazioni qubit ####

Oltre alle operazioni Single-qubit precedenti, il preludio definisce anche diverse operazioni multiqubit.

Per prima cosa, l' <xref:Microsoft.Quantum.Intrinsic.CNOT> operazione esegue un controllo- `NOT` Gate standard, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Bmatrix}.
\end{Equation} dispone della firma `((Qubit, Qubit) => Unit is Adj + Ctl)` , che rappresenta che $ \operatorname{CNOT} $ agisce unitarily su due qubits singoli.
`CNOT(q1, q2)` è uguale a `(Controlled X)([q1], q2)`.
Poiché il `Controlled` functor consente il controllo in un registro, viene usato il valore letterale `[q1]` di matrice per indicare che si vuole solo il controllo.

L' <xref:Microsoft.Quantum.Intrinsic.CCNOT> operazione esegue il controllo non gestito doppiamente, talvolta noto anche come Toffoli Gate.
Dispone della firma `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .
`CCNOT(q1, q2, q3)` è uguale a `(Controlled X)([q1, q2], q3)`.

L' <xref:Microsoft.Quantum.Intrinsic.SWAP> operazione scambia gli Stati del quantum di due qubits.
Ovvero implementa la matrice unitaria \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{Bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Bmatrix}.
\end{Equation} dispone della firma `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)` equivale a `CNOT(q1, q2)` seguito da `CNOT(q2, q1)` e quindi da `CNOT(q1, q2)` .

> [!NOTE]
> Lo scambio *non* corrisponde alla ridisposizione degli elementi di una variabile di tipo `Qubit[]` .
> Se si applica, viene apportata `SWAP(q1, q2)` una modifica allo stato di qubits a cui fa riferimento `q1` e `q2` , mentre `let swappedRegister = [q2, q1];` influiscono solo sul modo in cui si fa riferimento a tali qubits.
> Consente inoltre `(Controlled SWAP)([q0], (q1, q2))` `SWAP` di condizionare lo stato di un terzo qubit, che non è possibile rappresentare ridisponendo gli elementi.
> Il Gate di scambio controllato, noto anche come Fredkin Gate, è sufficientemente potente da includere tutti i calcoli classici.

Infine, il preludio fornisce due operazioni per la rappresentazione esponenziale degli operatori qubit di Pauli.
L' <xref:Microsoft.Quantum.Intrinsic.Exp> operazione esegue una rotazione basata su un prodotto tensore di matrici Pauli, come rappresentato dall'unità qubit \Begin{Equation} \operatorname{exp} (\vec{\sigma}, \Phi) \mathrel{: =} \exp\left (i \phi sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} in cui $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ è una sequenza di operatori di sola qubit Pauli e dove $ \Phi $ è un angolo.
La `Exp` rotazione rappresenta $ \vec{\sigma} $ come matrice di `Pauli` elementi, in modo che disponga della firma `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

L' <xref:Microsoft.Quantum.Intrinsic.ExpFrac> operazione esegue la stessa rotazione, usando la notazione della frazione diadico descritta in precedenza.
Dispone della firma `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .

> [!WARNING]
> Gli esponenziali del prodotto tensore degli operatori di Pauli non sono uguali ai prodotti tensori delle esponenziali degli operatori Pauli.
> Ovvero $e ^ {i (Z \otimes Z) \Phi} \ne e ^ {i Z \Phi} \otimes e ^ {i Z \Phi} $.

### <a name="measurements"></a>Misurazioni ###

Quando si esegue la misurazione, il valore + 1 autovalore dell'operatore da misurare corrisponde a un `Zero` risultato e il valore-1 autovalore a un `One` risultato.

> [!NOTE]
> Sebbene la Convenzione possa sembrare dispari, presenta due vantaggi molto interessanti.
> Per prima cosa, l'osservazione del risultato $ \ket {0} $ è rappresentata dal `Result` valore `Zero` , mentre l'osservazione {1} di $ \ket $ corrisponde a `One` .
> In secondo luogo, è possibile scrivere che autovalore $ \lambda $ corrispondente a un risultato $r $ is $ \lambda = (-1) ^ r $.

Le operazioni di misurazione supportano né né il `Adjoint` `Controlled` functore.

L' <xref:Microsoft.Quantum.Intrinsic.Measure> operazione esegue una misurazione congiunta di uno o più qubits nel prodotto specificato di operatori Pauli.
Se la matrice di Pauli e la matrice qubit hanno lunghezze diverse, l'operazione ha esito negativo.
`Measure` dispone della firma `((Pauli[], Qubit[]) => Result)` .

Si noti che una misurazione congiunta non corrisponde alla misurazione di ogni singolo qubit.
Si consideri ad esempio lo stato $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.
Misurando $Z _0 $ e $Z _1 $ individualmente, si ottengono i risultati $r _0 = $1 e $r _1 = $1.
Misurando $Z _0 Z_1 $, tuttavia, viene ottenuto il risultato singolo $r _ {\textrm{joint}} = $0, che indica che la combinazione di $ \ket {11} $ è positiva.
Inserisci in modo diverso, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.
In modo critico, poiché si apprende *solo* la parità da questa misurazione, vengono mantenute tutte le informazioni sui quantum rappresentate nella superposizione tra gli stati 2 2-qubit della parità positiva, $ \ket {00} $ e $ \ket {11} $.
Questa proprietà sarà essenziale in un secondo momento, perché viene discussa la correzione degli errori.

Per praticità, il preludio fornisce anche altre due operazioni per la misurazione di qubits.
Innanzitutto, poiché l'esecuzione di misurazioni qubit è piuttosto comune, il preludio definisce una sintassi abbreviata per questo caso.
L' <xref:Microsoft.Quantum.Intrinsic.M> operazione misura l'operatore Pauli $Z $ in un singolo qubit e ha la firma `(Qubit => Result)` .
`M(q)` equivale a: `Measure([PauliZ], [q])`.

<xref:Microsoft.Quantum.Measurement.MultiM>Misura l'operatore Pauli $Z $ *separatamente* in ogni matrice di qubits, restituendo la *matrice* di `Result` valori ottenuti per ogni qubit.
In alcuni casi può essere ottimizzato. Dispone della firma ( `Qubit[] => Result[])` .
`MultiM(qs)` equivale a:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Funzioni di estensione e operazioni ##

Inoltre, il preludio definisce un set completo di funzioni matematiche e di conversione dei tipi a livello di .NET da usare all'interno del Q# codice.
Ad esempio, lo <xref:Microsoft.Quantum.Math> spazio dei nomi definisce operazioni utili, ad esempio <xref:Microsoft.Quantum.Math.Sin> e <xref:Microsoft.Quantum.Math.Log> .
L'implementazione fornita da Quantum Development Kit usa la classica libreria di classi base .NET e pertanto può comportare una comunicazione aggiuntiva round trip tra i programmi Quantum e i driver classici.
Sebbene non sia presente un problema per un simulatore locale, può trattarsi di un problema di prestazioni quando si usa un simulatore remoto o un hardware effettivo come computer di destinazione.
Ciò premesso, è possibile che un singolo computer di destinazione rilevi questo effetto, eseguendo l'override di queste operazioni con versioni più efficienti per quel particolare sistema.

### <a name="math"></a>Math ###

Lo <xref:Microsoft.Quantum.Math> spazio dei nomi fornisce molte funzioni utili della [ `System.Math` classe](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true)della libreria di classi base .NET.
Queste funzioni possono essere utilizzate allo stesso modo di qualsiasi altra Q# funzione:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Se un metodo statico .NET è stato sottoposto a overload in base al tipo degli argomenti, la Q# funzione corrispondente viene annotata con un suffisso che indica il tipo di input:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Operazioni bit per bit ###

Infine, lo <xref:Microsoft.Quantum.Bitwise> spazio dei nomi fornisce diverse funzioni utili per la modifica di numeri interi tramite operatori bit per bit.
Ad esempio, <xref:Microsoft.Quantum.Bitwise.Parity> restituisce la parità bit per bit di un Integer come un altro numero intero.
