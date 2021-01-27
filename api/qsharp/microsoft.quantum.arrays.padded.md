---
uid: Microsoft.Quantum.Arrays.Padded
title: Funzione riempita
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845555"
---
# <a name="padded-function"></a>Funzione riempita

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce una matrice riempita con i valori specificati fino a una lunghezza specificata.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="nelementstotal--int"></a>nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)

Lunghezza della matrice riempita. Se questo è positivo, `inputArray` viene riempito alla testa. Se si tratta di un valore negativo, `inputArray` viene riempito alla fine della coda.


### <a name="defaultelement--t"></a>impostazione predefinita:' t

Valore predefinito da usare per gli elementi di riempimento.


### <a name="inputarray--t"></a>inputArray:' t []

Matrice i cui valori si trovano all'inizio della matrice di output.



## <a name="output--t"></a>Output:' t []

Matrice `output` `inputArray` riempita all'inizio con `defaultElement` s finché non `output` ha lunghezza `nElementsTotal`

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi della matrice.

## <a name="example"></a>Esempio

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```