---
uid: Microsoft.Quantum.Arrays.Exclude
title: Escludi funzione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719283"
---
# <a name="exclude-function"></a>Escludi funzione

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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