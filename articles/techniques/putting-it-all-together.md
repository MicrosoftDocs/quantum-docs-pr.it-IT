---
title: Tecniche Q - Mettere tutto insieme
description: Passeggiata attraverso un programma di base di Q , che dimostra il teletrasporto quantistico.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030566"
---
# <a name="putting-it-all-together-teleportation"></a>Mettere tutto insieme: teletrasporto #
Torniamo all'esempio del circuito di teletrasporto definito in [Circuiti Quantici](xref:microsoft.quantum.concepts.circuits). Useremo questo per illustrare i concetti che abbiamo imparato finora. Una spiegazione del teletrasporto quantistico è fornita di seguito per coloro che non hanno familiarità con la teoria, seguita da una procedura dettagliata dell'implementazione del codice in Q . 

## <a name="quantum-teleportation-theory"></a>Teletrasporto quantico: Teoria
Il teletrasporto quantistico è una tecnica per l'invio di uno stato quantico sconosciuto (che ci riferiremo come il '__messaggio__') da un qubit in una posizione a un qubit in un'altra posizione (faremo riferimento a questi qubit come '__qui__' e '__lì__', rispettivamente). Possiamo rappresentare il nostro __messaggio__ come un vettore utilizzando la notazione Dirac: 

"Ket" , "psi" , "alpha"{0} , "beta" e "", ""ket"{1}

Lo stato del __qubit__ del messaggio è sconosciuto a noi come non conosciamo i valori di "alpha" e "beta" .

### <a name="step-1-create-an-entangled-state"></a>Passaggio 1: Creare uno stato aggrovigliatoStep 1: Create an entangled state
Al fine di inviare il __messaggio__ abbiamo bisogno per il qubit __qui__ per essere impigliato con il qubit __lì__. Ciò si ottiene applicando un cancello Hadamard, seguito da un cancello CNOT. Diamo un'occhiata alla matematica dietro queste operazioni cancello.

Inizieremo con i qubit __qua__ e __là__ sia{0}nello stato di "ket". Dopo aver impacchetto questi qubit, sono nello stato:

"Ket"{1}, "phi" e "ph",{2}{00} {11}"in ccomp".

### <a name="step-2-send-the-message"></a>Passaggio 2: Inviare il messaggio
Per inviare il __messaggio,__ prima applichiamo un gate CNOT con il __qubit__ del messaggio e __qui__ qubit come input (il qubit del __messaggio__ è il controllo e il qubit __qui__ è il qubit di destinazione, in questo caso). Questo stato di input può essere scritto:This input state can be written:

- "ket" , "setro"{0} o "ket"{1}{1}{2}{00} {11}( )

Questo si espande a:

"ket"{2}, "ket" , "setro" , "setro" , "phi"{000} {2}{011} {2}{100} {2}{111} , ".

Come promemoria, il cancello CNOT capovolge il qubit di destinazione quando il qubit di controllo è 1. Quindi, ad esempio, un input{000}di , ovvero un valore di "ket", non comporterà alcuna modifica in quanto il primo qubit (il controllo) è 0. Tuttavia, prendere un caso in cui il primo qubit è{100}1 - per esempio un input di . In questo caso, l'output{110}è il file ,ket, poiché il secondo qubit (la destinazione) viene capovolto dal gate CNOT.

Consideriamo ora il nostro output una volta che il cancello CNOT ha agito sul nostro input sopra. Il risultato è:

"frac" , alfa{2}, sqrt ,{000} sqrt , sqt{2}{011} {2}{101} , alpha , sqrt , ket{2}{110} , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , ,

Il passaggio successivo per inviare il __messaggio__ consiste nell'applicare una porta Hadamard al __qubit__ del messaggio (questo è il primo qubit di ogni termine). 

Come promemoria, la porta Hadamard fa quanto segue:

Input | Output
---------------------------| ---------------------------------------------------------------
N. di{0}dollari per il tallustio.  | "frac"{1}(""terrore"{2}("ket"{0} {1})
N. di{1}dollari per il tallustio.  | (-tt){1}{2}{0} {1}

Se applichiamo la porta Hadamard al primo qubit di ogni termine del nostro output precedente, otteniamo il seguente risultato:

{2}Per il tipo di telefono, sqrt, si sqrt{1}{2}{0} {1}{00} {2}{1}{2}{0} {1}{11} ( . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .{2}. . .{1}. .{2}. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . ('''questo').{0} {1}{10} {2}{1}{2}{0} {1}{01}

Si noti che per ogni{1}termine sono{2}presenti due fattori di tipo .frac. Possiamo moltiplicarli dando il seguente risultato:

"frac" ('ket'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''{2}{0} {1}{00} {2}{0} {1}{11} {2}{0} {1}{10} {2}{0} {1}{01}

Il fattore{1}{2}di frac è comune a ogni termine in modo che ora possiamo portarlo al di fuori delle parentesi quadre:

"frac"{1}{2}[-grande[ , alfa{0} ( ,{1}xket{00} ) , ket{0} , alfa ({1}{11} {0} {1}{10} {0} {1}{01}, , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , ,

Possiamo quindi moltiplicare le staffe per ogni termine dando:

{1}{2}"frac" ["grande" [ .{000} {100} {011} {111} {010} {110} {001} {101}. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

### <a name="step-3-measure-the-result"></a>Passaggio 3: Misurare il risultatoStep 3: Measure the result

A causa di __qua__ e __là__ essere impigliato, qualsiasi misura __qui__ influenzerà lo stato di __lì__. Se misuriamo il primo e il secondo qubit (__messaggio__ e __qui__) possiamo imparare in quale stato __c'è,__ a causa di questa proprietà di impigliamento. 

* Se misuriamo e otteniamo un risultato 00, la sovrapposizione collassa, lasciando solo termini coerenti con questo risultato. Questo è il valore di{000} "alpha" o{001}"beta". È possibile eseguire il refactoring{00}di questo file{0} nel percorso di{1}addizione in . Pertanto, se si misura il primo e il secondo qubit a 00, sappiamo che il{0} terzo qubit,{1} __c'è__, è nello stato .
* Se misuriamo e otteniamo un risultato 01, la sovrapposizione collassa, lasciando solo termini coerenti con questo risultato. Questo è il valore di{011} "alpha" o{010}"beta". È possibile eseguire il refactoring{01}di questo file{1} nel percorso di{0}addizione in . Pertanto, se si misura il primo e il secondo qubit per essere 01, sappiamo che il terzo qubit, __c'è__, è nello stato .{1} {0}
* Se misuriamo e otteniamo un risultato 10, la sovrapposizione collassa, lasciando solo termini coerenti con questo risultato. Che è alfa-ket{100} - beta -ket{101}. È possibile eseguire il refactoring{10}di questo file{0} a{1}. Pertanto, se si misura il primo e il secondo qubit per essere 10, sappiamo che il terzo qubit, __c'è__, è nello stato .{0} {1}
* Se misuriamo e otteniamo un risultato 11, la sovrapposizione collassa, lasciando solo termini coerenti con questo risultato. Che è alfa-ket{111} - beta -ket{110}. È possibile eseguire il refactoring{11}di questo file{1} a{0}. Pertanto, se si misura il primo e il secondo qubit per essere 11, sappiamo che il terzo qubit, __c'è__, è nello stato .{1} {0}

### <a name="step-4-interpret-the-result"></a>Passaggio 4: Interpretare il risultatoStep 4: Interpret the result

Come promemoria, il __messaggio__ originale che volevamo inviare era:

"Ket" , "psi" , "alpha"{0} , "beta" e "", ""ket"{1}

Abbiamo bisogno di ottenere il __qubit lì__ in questo stato, in modo che lo stato ricevuto è quello che è stato destinato. 

* Se abbiamo misurato e ottenuto un risultato di 00, quindi il terzo qubit, __c'è__, è nello stato .{0} {1} Poiché questo è il __messaggio__previsto, non è necessaria alcuna modifica.
* Se abbiamo misurato e ottenuto un risultato di 01, quindi il terzo qubit, __c'è__, è nello stato .{1} {0} Questo è diverso dal __messaggio__previsto , tuttavia l'applicazione di un gate{0} NOT ci dà{1}lo stato desiderato .
* Se abbiamo misurato e ottenuto un risultato di 10, quindi il terzo qubit, __c'è__, è nello stato .{0} {1} Questo è diverso dal __messaggio__desiderato , tuttavia l'applicazione di un gate{0} di z ci{1}dà lo stato desiderato .
* Se abbiamo misurato e ottenuto un risultato di 11, quindi il terzo qubit, __c'è__, è nello stato .{1} {0} Questo è diverso dal __messaggio__previsto , tuttavia l'applicazione di un gate NOT seguito{0} da un gate{1}di z ci dà lo stato desiderato .

Per riassumere, se misuriamo e il primo qubit è 1, viene applicato un gate . Se misuriamo e il secondo qubit è 1, viene applicato un cancello NON.

### <a name="summary"></a>Summary
Di seguito è mostrato un circuito quantistico di libri di testo che implementa il teletrasporto. Spostandosi da sinistra a destra si può vedere:
- Passo 1: Entangling __qua__ e __là__ applicando un cancello Hadamard e un cancello CNOT.
- Passo 2: Invio del __messaggio__ utilizzando un cancello CNOT e un cancello Hadamard.
- Passo 3: Prendendo una misura del primo e secondo qubit, __messaggio__ e __qui__.
- Passo 4: Applicare un cancello NOT o un cancello , a seconda del risultato della misurazione nel passaggio 3.

!['Teleport(msg: Qubit, ci: Qubit) : Unità'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Teletrasporto quantico: Codice

Abbiamo il nostro circuito per il teletrasporto quantistico:

!['Teleport(msg: Qubit, ci: Qubit) : Unità'](~/media/teleportation.svg)

Ora possiamo tradurre ciascuno dei passaggi di questo circuito quantistico in Q.

### <a name="step-0-definition"></a>Fase 0: Definizione
Quando eseguiamo il teletrasporto, dobbiamo conoscere il __messaggio__ che vogliamo inviare, e dove vogliamo inviarlo __(lì__). Per questo motivo, iniziamo definendo una nuova operazione di teletrasporto che viene dato due qubit come argomenti, `msg` e `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Abbiamo anche bisogno di `here` allocare un `using` qubit che otteniamo con un blocco:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Passaggio 1: Creare uno stato aggrovigliatoStep 1: Create an entangled state
Possiamo quindi creare la coppia `here` impigliata tra e `there` utilizzando le @"microsoft.quantum.intrinsic.h" operazioni e @"microsoft.quantum.intrinsic.cnot" :

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Passaggio 2: Inviare il messaggio
Per spostare il qubit del messaggio, viene quindi utilizzato i successivi gate di $H tipo nomeoperatore E CNOT:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Fase 3 & 4: Misurare e interpretare il risultato
Infine, utilizziamo @"microsoft.quantum.intrinsic.m" per eseguire le misurazioni ed eseguire le operazioni di `if` gate necessarie per ottenere lo stato desiderato, come indicato da istruzioni:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>Passaggio 5: Riavviare il registro qubitStep 5: Restarting the qubit register

Alla fine di ogni operazione di Q, è necessario lasciare che{0}i qubit nello stato di errore "ket". Possiamo usare @"microsoft.quantum.intrinsic.reset" per riavviare tutti i qubit allo stato zero e questo terminerà la nostra operazione.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


