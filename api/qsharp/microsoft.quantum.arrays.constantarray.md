---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846235"
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



## <a name="example"></a>Esempio

Il codice seguente crea una matrice di 3 valori booleani, ognuno dei quali è uguale a `true` :

```qsharp
let array = ConstantArray(3, true);
```