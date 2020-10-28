---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719070"
---
# <a name="lookupfunction-function"></a>LookupFunction (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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