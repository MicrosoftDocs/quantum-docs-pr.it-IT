---
uid: Microsoft.Quantum.Arrays.Exclude
title: Escludi funzione
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848670"
---
# <a name="exclude-function"></a>Escludi funzione

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce una matrice contenente gli elementi di un'altra matrice, esclusi gli elementi in un determinato elenco di indici.

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="remove--int"></a>Remove: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice di indici che indica gli elementi che devono essere esclusi dall'output.


### <a name="array--t"></a>matrice:' t []

Matrice di cui vengono presi i valori nella matrice di output.



## <a name="output--t"></a>Output:' t []

Matrice `output` che `output[0]` rappresenta il primo elemento di `array` il cui indice non è presente in `remove` , ovvero `output[1]` il secondo elemento e così via.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi della matrice.

## <a name="example"></a>Esempio

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```