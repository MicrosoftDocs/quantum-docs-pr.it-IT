---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funzione Permutation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220927"
---
# <a name="ispermutation-function"></a>Funzione Permutation

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce true se e solo se una determinata matrice rappresenta una permutazione.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Descrizione

Data una matrice `array` di lunghezza `n` , restituisce true solo se ogni intero da `0` a `n - 1` viene visualizzato esattamente una volta in `array` , in modo che `array` possa essere interpretato come una permutazione sugli `n` elementi.

## <a name="input"></a>Input

### <a name="permuation--int"></a>permuation: [int](xref:microsoft.quantum.lang-ref.int)[]

Matrice che può rappresentare o meno una permutazione.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Commenti

Una matrice di lunghezza zero è una permutazione.