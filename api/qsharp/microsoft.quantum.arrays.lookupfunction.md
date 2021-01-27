---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845690"
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