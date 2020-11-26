---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operazione ApplyBlockEncodingByLCU
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225483"
---
# <a name="applyblockencodingbylcu-operation"></a>Operazione ApplyBlockEncodingByLCU

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementazione di `BlockEncodingByLCU`.

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL




### <a name="selector--ts--unit--is-adj--ctl"></a>selettore: (t, s) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL




### <a name="auxiliary--t"></a>ausiliario:' t




### <a name="system--s"></a>sistema:





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="s"></a>Gli

