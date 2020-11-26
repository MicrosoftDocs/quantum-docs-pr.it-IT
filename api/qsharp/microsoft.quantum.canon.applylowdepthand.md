---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Operazione ApplyLowDepthAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209316"
---
# <a name="applylowdepthand-operation"></a>Operazione ApplyLowDepthAnd

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inverte un qubit di destinazione specificato se e solo se entrambi i qubits di controllo si trovano nello stato 1, con T-depth 1, usando la misurazione per eseguire l'operazione di aggiunta.

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Inverte `target` se e solo se entrambi i controlli sono pari a 1, ma presuppone che `target` si trovi nello stato 0.  L'operazione ha T-Count 4, T-depth 1 e richiede un qubit helper e può pertanto essere preferibile a un'operazione CCNOT, se `target` è noto come 0.  Il contiguo di questa operazione è basato sulla misurazione e non richiede alcun controllo T e nessun qubit helper.

## <a name="input"></a>Input

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo controllo qubit


### <a name="control2--qubit"></a>controllo2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Secondo qubit di controllo


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ausiliari di destinazione; deve essere nello stato 0



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

- Cody Jones: "costruzioni innovative per il controllo Toffoli A tolleranza di errore", fisico. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328
- Peter Selinger: "Quantum Circuits of T-Depth One", fisico. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) DOI: 10.1103/PhysRevA. 87.042302