---
uid: Microsoft.Quantum.Arrays.Chunks
title: Blocchi (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719466"
---
# <a name="chunks-function"></a>Blocchi (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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