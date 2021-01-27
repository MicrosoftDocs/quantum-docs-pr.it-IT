---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848631"
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

## <a name="example"></a>Esempio

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```