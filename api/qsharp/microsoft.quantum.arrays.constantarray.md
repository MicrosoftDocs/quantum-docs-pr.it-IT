---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719415"
---
# <a name="constantarray-function"></a>ConstantArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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

