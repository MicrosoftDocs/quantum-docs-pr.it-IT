---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Operazione DrawMany
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846213"
---
# <a name="drawmany-operation"></a>Operazione DrawMany

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzato un Integer, data un'operazione che esegue il campionamento di un solo bit alla volta.

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)