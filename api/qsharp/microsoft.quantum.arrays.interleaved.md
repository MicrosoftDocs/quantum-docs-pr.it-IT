---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funzione Interleaved
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848105"
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

## <a name="example"></a>Esempio

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```