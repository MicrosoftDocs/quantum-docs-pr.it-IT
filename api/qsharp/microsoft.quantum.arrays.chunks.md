---
uid: Microsoft.Quantum.Arrays.Chunks
title: Blocchi (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221607"
---
# <a name="chunks-function"></a>Blocchi (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Suddivide una matrice in più parti di uguale lunghezza.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Input

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)

Lunghezza di ogni blocco.


### <a name="arr--t"></a>arr:' t []

Matrice da suddividere.



## <a name="output--t"></a>Output:' t [] []

Matrice contenente ogni blocco della matrice originale.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Si noti che l'ultimo elemento dell'output può essere minore di `nElements` se `Length(arr)` non è divisibile da `nElements` .