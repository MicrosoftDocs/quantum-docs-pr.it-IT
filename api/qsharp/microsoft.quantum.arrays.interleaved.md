---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funzione Interleaved
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220961"
---
# <a name="interleaved-function"></a>Funzione Interleaved

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Interleaves due matrici di (quasi) stesse dimensioni.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Descrizione

Questa funzione restituisce l'interfoliazione di due matrici, a partire dal primo elemento della prima matrice, dal primo elemento della seconda matrice e così via.

La prima matrice deve avere la stessa lunghezza del secondo oppure può avere un altro elemento.

## <a name="input"></a>Input

### <a name="first--t"></a>primo:' t []

Prima matrice da Interleave.


### <a name="second--t"></a>secondo:' t []

Seconda matrice da Interleave.



## <a name="output--t"></a>Output:' t []

Matrice Interleaved

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di ogni elemento di `first` e `second` .