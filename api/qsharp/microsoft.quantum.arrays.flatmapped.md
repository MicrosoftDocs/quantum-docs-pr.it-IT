---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221250"
---
# <a name="flatmapped-function"></a>FlatMapped (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice e una funzione che esegue il mapping di un elemento di matrice a una matrice di output, restituisce le matrici di output concatenate per ogni elemento della matrice.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Input

### <a name="mapper--tinput---toutput"></a>Mapper:' TInput->' TOutput []

Funzione da `'TInput` a `'TOutput[]` utilizzata per eseguire il mapping degli elementi di matrice.


### <a name="array--tinput"></a>matrice:' TInput []

Matrice di elementi.



## <a name="output--toutput"></a>Output:' TOutput []

Matrice di `'TOutput[]` che rappresenta la concatenazione di tutte le matrici generate dalla funzione di mapping.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="tinput"></a>' TInput

Tipo di `array` elementi.
### <a name="toutput"></a>' TOutput

La `mapper` funzione restituisce matrici di questo tipo.