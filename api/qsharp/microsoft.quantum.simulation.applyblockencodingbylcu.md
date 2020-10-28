---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operazione ApplyBlockEncodingByLCU
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722127"
---
# <a name="applyblockencodingbylcu-operation"></a>Operazione ApplyBlockEncodingByLCU

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Implementazione di `BlockEncodingByLCU`.

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>Input

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL




### <a name="selector--ts--unit-adj--ctl"></a>selettore: (t, s) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL




### <a name="auxiliary--t"></a>ausiliario:' t




### <a name="system--s"></a>sistema:





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="s"></a>Gli

