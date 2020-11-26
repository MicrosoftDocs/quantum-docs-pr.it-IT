---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210064"
---
# <a name="constantarray-function"></a>ConstantArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una matrice di lunghezza specificata con tutti gli elementi uguali al valore specificato.

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>Input

### <a name="length--int"></a>Lunghezza: [int](xref:microsoft.quantum.lang-ref.int)

Lunghezza della nuova matrice.


### <a name="value--t"></a>valore:' t

Valore di ogni elemento della nuova matrice.



## <a name="output--t"></a>Output:' t []

Una nuova matrice di lunghezza `length` , in modo che ogni elemento sia `value` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

