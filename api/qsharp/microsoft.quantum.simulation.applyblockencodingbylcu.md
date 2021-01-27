---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operazione ApplyBlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852817"
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

