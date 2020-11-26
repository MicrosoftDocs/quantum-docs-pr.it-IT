---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funzione Prefixes
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220390"
---
# <a name="prefixes-function"></a>Funzione Prefixes

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data una matrice, restituisce tutti i relativi prefissi.

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>Descrizione

Restituisce una matrice di tutti i prefissi, a partire da una matrice che contiene solo il primo elemento fino alla matrice completa.

## <a name="input"></a>Input

### <a name="array--t"></a>matrice:' t []

Matrice di elementi.



## <a name="output--t"></a>Output:' t [] []



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.