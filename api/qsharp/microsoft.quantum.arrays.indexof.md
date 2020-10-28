---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Funzione IndexOf
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719175"
---
# <a name="indexof-function"></a>Funzione IndexOf

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Restituisce il primo indice del primo elemento di una matrice che soddisfa un predicato specificato. Se tale elemento non esiste, restituisce-1.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Input

### <a name="predicate--t---bool"></a>predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione di predicato che agisce sugli elementi della matrice.


### <a name="arr--t"></a>arr:' t []

Matrice da cercare utilizzando il predicato specificato.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Indice più piccolo in `idx` modo che `predicate(arr[idx])` sia true oppure-1 se tale elemento non esiste.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

