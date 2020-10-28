---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719250"
---
# <a name="flatmapped-function"></a>FlatMapped (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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