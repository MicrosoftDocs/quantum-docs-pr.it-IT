---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equala (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848697"
---
# <a name="equala-function"></a>Equala (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Date due matrici dello stesso tipo e un predicato definito per coppie di elementi delle matrici, verifica se le matrici sono uguali.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Input

### <a name="equal--tt---bool"></a>uguale a: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione dalla tupla `('T, 'T)` a `Bool` utilizzata per verificare se due elementi delle matrici sono uguali.


### <a name="array1--t"></a>Matrice1:' t []

Prima matrice da confrontare.


### <a name="array2--t"></a>Matrice2:' t []

Seconda matrice da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

Valore `true` se e solo se `array1` e `array2` sono uguali.
Ovvero, se entrambe le matrici hanno la stessa lunghezza e tutti gli elementi sono uguali a quanto definito da `equal` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di elementi di ogni matrice.

## <a name="example"></a>Esempio

Il codice seguente controlla se coppie di matrici diverse sono uguali:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>Commenti

Questa funzione è definita per i tipi generici; ad esempio, ogni volta che sono presenti due matrici `'T[]` e una funzione `equal: ('T, 'T) -> Bool` , questa funzione restituisce un `Bool` valore che indica se le matrici sono uguali.
Affinché due matrici siano considerate uguali, devono avere la stessa lunghezza e gli elementi nelle stesse posizioni nelle matrici devono essere uguali.