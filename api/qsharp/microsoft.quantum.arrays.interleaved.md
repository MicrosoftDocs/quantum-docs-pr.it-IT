---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funzione Interleaved
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719142"
---
# <a name="interleaved-function"></a>Funzione Interleaved

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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