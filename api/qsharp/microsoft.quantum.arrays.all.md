---
uid: Microsoft.Quantum.Arrays.All
title: All (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842889"
---
# <a name="all-function"></a>All (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice e un predicato definito per gli elementi della matrice e controlla se tutti gli elementi della matrice soddisfano il predicato.

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Input

### <a name="predicate--t---bool"></a>predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione da `'T` a `Bool` utilizzata per controllare gli elementi.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`Valore della funzione e del predicato applicato a tutti gli elementi.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.

## <a name="example"></a>Esempio

Il codice seguente controlla se tutti gli elementi della matrice sono diversi da zero:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a>Commenti

La funzione è definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `predicate: 'T -> Bool` possibile produrre un `Bool` valore che indica se tutti gli elementi soddisfano `predicate` .