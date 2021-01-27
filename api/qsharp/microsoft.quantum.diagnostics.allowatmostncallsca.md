---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Operazione AllowAtMostNCallsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853530"
---
# <a name="allowatmostncallsca-operation"></a>Operazione AllowAtMostNCallsCA

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tra una chiamata a questa operazione e la relativa contigua, asserisce che una determinata operazione viene chiamata al massimo un certo numero di volte.

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a>Input

### <a name="ntimes--int"></a>nTimes: [int](xref:microsoft.quantum.lang-ref.int)

Il numero massimo di volte che è `op` possibile chiamare.


### <a name="op--tinput--toutput--is-adj--ctl"></a>op:' TInput =>' TOutput è ADJ + CTL

Operazione le cui chiamate devono essere limitate.


### <a name="message--string"></a>messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)

Messaggio da visualizzare in caso di errore.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput



## <a name="example"></a>Esempio

Il frammento di codice seguente avrà esito negativo quando viene eseguito nei computer che supportano questa diagnostica:

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a>Commenti

Questa operazione può essere sostituita da un no-op sulle destinazioni che non lo supportano.