---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Funzione Permutation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848101"
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



## <a name="example"></a>Esempio

Il codice Q # seguente stampa il messaggio "tutti i dati di diagnostica sono stati completati correttamente":

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>Commenti

Una matrice di lunghezza zero è una permutazione.