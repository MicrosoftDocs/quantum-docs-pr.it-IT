---
title: 'Tecniche d #-riunendoli | Microsoft Docs'
description: 'Tecniche d #-riunendole'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f65b3e260f98a7a90da13b62edd6cc63d200f5af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183268"
---
# <a name="putting-it-all-together-teleportation"></a>Riunendoli: Teleporting #
Torniamo all'esempio del circuito di Teleporting definito nei [circuiti Quantum](xref:microsoft.quantum.concepts.circuits). Questa operazione verrà usata per illustrare i concetti appresi finora. Di seguito è riportata una spiegazione del teleportamento del quantum per coloro che non hanno familiarità con la teoria, seguito da una procedura dettagliata dell'implementazione del codice in Q #. 

## <a name="quantum-teleportation-theory"></a>Teleportation Quantum: teoria
La teleportazione quantistica è una tecnica per l'invio di uno stato quantum sconosciuto (a cui si farà riferimento come "__messaggio__") da un qubit in una posizione a una qubit in un'altra posizione (si farà riferimento a questi qubits come '__here__' è__There__', rispettivamente). È possibile rappresentare il __messaggio__ come vettore usando la notazione Dirac: 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Lo stato del __messaggio__ qubit non è noto perché non sono noti i valori di $ \Alpha $ e $ \beta $.

### <a name="step-1-create-an-entangled-state"></a>Passaggio 1: creare uno stato incastrato
Per inviare il __messaggio__ __, è__necessario che __il qubit sia presente in questo punto__ di qubit. Questa operazione viene eseguita applicando un Hadamard Gate, seguito da un CNOT Gate. Esaminiamo i calcoli alla base di queste operazioni Gate.

Si inizierà con il qubits in __questo__ punto e __ci__ si troverà entrambi nello stato $ \ket{0}$. Dopo aver coinvolto questi qubits, si trovano nello stato:

$ $ \ket{\Phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>Passaggio 2: inviare il messaggio
Per inviare il __messaggio__ , viene prima di tutto applicato un CNOT Gate con il __messaggio__ qubit e __qui__ qubit come input (il __messaggio__ qubit è il controllo e __qui__ qubit è il qubit di destinazione, in questa istanza). È possibile scrivere questo stato di input:

$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $

Questa operazione si espande a:

$ $ \ket{\psi}\ket{\Phi ^ +} = \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

Come promemoria, il CNOT Gate capovolge il qubit di destinazione quando il controllo qubit è 1. Quindi, ad esempio, un input di $ \ket{000}$ non comporterà alcuna modifica, perché il primo qubit (il controllo) è 0. Tuttavia, se il primo qubit è 1, ad esempio un input di $ \ket{100}$. In questo caso, l'output è $ \ket{110}$ come il secondo qubit (la destinazione) viene capovolto dal CNOT Gate.

Si consideri ora l'output dopo che CNOT Gate ha agito sull'input precedente. Il risultato è:

$ $ \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

Il passaggio successivo per inviare il __messaggio__ consiste nell'applicare un Hadamard Gate al __messaggio__ qubit (il primo qubit di ogni termine). 

Come promemoria, il Hadamard Gate esegue le operazioni seguenti:

Input | Output
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $

Se si applica il Hadamard Gate alla prima qubit di ogni termine dell'output precedente, viene visualizzato il risultato seguente:

$ $ \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{ \sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

Si noti che ogni termine ha $2 \frac{1}{\sqrt{2}} $ factors. Possiamo moltiplicarli per ottenere il risultato seguente:

$ $ \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

Il{1}$ \frac {2}$ Factor è comune a ogni termine, quindi è ora possibile utilizzarlo all'esterno delle parentesi quadre:

$ $ \frac{1}{2}\Big [\Alpha (\ket{0} + \ket{1}) \ket{00} + \Alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\Big] $ $

Possiamo quindi moltiplicare le parentesi per ogni termine fornendo:

$ $ \frac{1}{2}\Big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\Big] $ $

### <a name="step-3-measure-the-result"></a>Passaggio 3: misurare il risultato

A causa di questo __errore, qualsiasi__ misurazione in __questa__ posizione influirà sullo __stato.__ Se misuriamo il primo e il secondo qubit (__Message__ e __here__) possiamo scoprire quale stato è __presente__ in, a causa di questa proprietà dell'operazione. 

* Se misuriamo e otteniamo un risultato 00, la superposizione viene compressa, lasciando solo i termini coerenti con questo risultato. Questo è $ \alpha\ket{000} + \beta\ket{001}$. Questa operazione può essere sottoposta a refactoring in $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $. Pertanto, se misuriamo il primo e il secondo qubit a 00, sappiamo che il terzo qubit è __presente__nello stato $ (\alpha\ket{0} + \beta\ket{1}) $.
* Se si misura e si ottiene un risultato 01, la superposizione viene compressa, lasciando solo i termini coerenti con questo risultato. Questo è $ \alpha\ket{011} + \beta\ket{010}$. Questa operazione può essere sottoposta a refactoring in $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $. Pertanto __, se__misuriamo il primo e il secondo qubit come 01, sappiamo che il terzo qubit è nello stato $ (\alpha\ket{1} + \beta\ket{0}) $.
* Se misuriamo e otteniamo il risultato 10, la superposizione viene compressa, lasciando solo i termini coerenti con questo risultato. Questo è $ \alpha\ket{100}-\beta\ket{101}$. Questa operazione può essere sottoposta a refactoring in $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $. Pertanto __, se__misuriamo il primo e il secondo qubit come 10, sappiamo che il terzo qubit è nello stato $ (\alpha\ket{0}-\beta\ket{1}) $.
* Se misuriamo e otteniamo il risultato 11, la superposizione viene compressa, lasciando solo i termini coerenti con questo risultato. Questo è $ \alpha\ket{111}-\beta\ket{110}$. Questa operazione può essere sottoposta a refactoring in $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $. Pertanto, se misuriamo il primo e il secondo qubit come 11, sappiamo che il terzo qubit, __c'__ è nello stato $ (\alpha\ket{1}-\beta\ket{0}) $.

### <a name="step-4-interpret-the-result"></a>Passaggio 4: interpretare il risultato

Come promemoria, il __messaggio__ originale che avremmo voluto inviare era:

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Dobbiamo ottenere lo __stato qubit in__ questo stato, in modo che lo stato ricevuto sia quello desiderato. 

* Se è stato misurato e ottenuto un risultato pari a __00, il__terzo qubit è nello stato $ (\alpha\ket{0} + \beta\ket{1}) $. Poiché si tratta del __messaggio__previsto, non è necessaria alcuna modifica.
* Se è stato misurato e ottenuto il risultato di __01, il__terzo qubit è nello stato $ (\alpha\ket{1} + \beta\ket{0}) $. Questo comportamento è diverso rispetto al __messaggio__previsto, tuttavia l'applicazione di un controllo not consente di ottenere lo stato desiderato $ (\alpha\ket{0} + \beta\ket{1}) $.
* Se è stato misurato e ottenuto il risultato di __10, il__terzo qubit è nello stato $ (\alpha\ket{0}-\beta\ket{1}) $. Questo comportamento è diverso da quello __previsto,__ tuttavia l'applicazione di uno Z Gate indica lo stato desiderato $ (\alpha\ket{0} + \beta\ket{1}) $.
* Se è stato misurato e ottenuto il risultato di __11, il__terzo qubit è nello stato $ (\alpha\ket{1}-\beta\ket{0}) $. Questo comportamento è diverso da quello __previsto,__ tuttavia l'applicazione di un controllo not seguito da un Gate Z indica lo stato desiderato $ (\alpha\ket{0} + \beta\ket{1}) $.

Per riepilogare, se si misura e il primo qubit è 1, viene applicato un controllo Z. Se misuriamo e il secondo qubit è 1, viene applicato un NOT Gate.

### <a name="summary"></a>Summary
Di seguito è riportato un circuito Quantum del libro di testo che implementa la teleportazione. Se si passa da sinistra a destra, è possibile vedere:
- Passaggio 1: eseguire __questa__ __operazione applicando__ un Hadamard Gate e CNOT Gate.
- Passaggio 2: invio del __messaggio__ tramite CNOT Gate e Hadamard Gate.
- Passaggio 3: esecuzione di una misurazione del primo e del secondo qubits, __messaggio__ e __qui__.
- Passaggio 4: applicazione di una funzione NOT Gate o Z Gate, a seconda del risultato della misurazione nel passaggio 3.

![' Teleport (msg: qubit, there: qubit): unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Teleportation Quantum: codice

Abbiamo il nostro circuito per la teleportazione quantistica:

![' Teleport (msg: qubit, there: qubit): unit '](~/media/teleportation.svg)

È ora possibile tradurre ogni passaggio in questo circuito Quantum in Q #.

### <a name="step-0-definition"></a>Passaggio 0: definizione
Quando si esegue la teleportazione, è necessario essere a conoscenza del __messaggio__ che si vuole inviare e__del punto in__cui si vuole inviarlo. Per questo motivo, si inizia definendo una nuova operazione Teleport a cui vengono assegnati due qubits come argomenti, `msg` e `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

È anche necessario allocare un `here` qubit che viene raggiunto con un blocco `using`:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Passaggio 1: creare uno stato incastrato
È quindi possibile creare una coppia di `here` e `there` con le operazioni di @"microsoft.quantum.primitive.h" e @"microsoft.quantum.primitive.cnot":

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Passaggio 2: inviare il messaggio
Si utilizzeranno quindi i successivi $ \operatorname{CNOT} $ e $H $ Gates per spostare il messaggio qubit:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Passaggio 3 & 4: misurazione e interpretazione del risultato
Infine, si usa @"microsoft.quantum.primitive.m" per eseguire le misurazioni ed eseguire le operazioni Gate necessarie per ottenere lo stato desiderato, come indicato dalle istruzioni `if`:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Termina la definizione dell'operatore di Teleporting, in modo da poter deallocare `here`, terminare il corpo e terminare l'operazione.

```qsharp
    }
}
```
