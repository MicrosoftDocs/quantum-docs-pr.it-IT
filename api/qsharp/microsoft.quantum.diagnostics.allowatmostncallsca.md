---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operazione AllowAtMostNCallsCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713065"
---
# <a name="allowatmostncallsca-operation"></a>Operazione AllowAtMostNCallsCA

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Tra una chiamata a questa operazione e la relativa contigua, asserisce che una determinata operazione viene chiamata al massimo un certo numero di volte.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a>Input

### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Il numero massimo di volte che è `op` possibile chiamare.


### <a name="op--tinput--toutput-adj--ctl"></a>op:' TInput =>' TOutput ADJ + CTL

Operazione le cui chiamate devono essere limitate.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Messaggio da visualizzare in caso di errore.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput



## <a name="remarks"></a>Commenti

Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.