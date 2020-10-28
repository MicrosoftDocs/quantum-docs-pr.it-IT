---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operazione DrawMany
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719370"
---
# <a name="drawmany-operation"></a>Operazione DrawMany

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Ripete un'operazione per un determinato numero di campioni, raccogliendo gli output in una matrice.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Input

### <a name="op--tinput--toutput"></a>op:' TInput =>' TOutput 

Operazione da chiamare ripetutamente.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

Numero di campioni di chiamata `op` a Collect.


### <a name="input--tinput"></a>input:' TInput

Input da passare a `op` .



## <a name="output--toutput"></a>Output:' TOutput []



## <a name="type-parameters"></a>Parametri di tipo

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)