---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funzione Permutation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719106"
---
# <a name="ispermutation-function"></a>Funzione Permutation

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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