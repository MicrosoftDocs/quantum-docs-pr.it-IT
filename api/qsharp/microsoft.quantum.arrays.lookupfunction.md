---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220774"
---
# <a name="lookupfunction-function"></a>LookupFunction (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice, restituisce una funzione che restituisce elementi della matrice.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Input

### <a name="array--t"></a>matrice:' t []

Matrice da rappresentare come funzione di ricerca.



## <a name="output--int---t"></a>Output: [int](xref:microsoft.quantum.lang-ref.int) -> t

Funzione di questo `f` tipo `f(idx) == f[idx]` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi della matrice rappresentata come funzione di ricerca.

## <a name="remarks"></a>Commenti

Questa funzione è particolarmente utile per l'interoperabilità con funzioni e operazioni che accettano `Int -> 'T` funzioni come argomenti. Si tratta di un'operazione comune, ad esempio, nella libreria di rappresentazione del generatore, in cui le funzioni vengono usate per evitare la necessità di registrare un'intera matrice in memoria.