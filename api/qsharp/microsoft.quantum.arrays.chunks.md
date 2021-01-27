---
uid: Microsoft.Quantum.Arrays.Chunks
title: Blocchi (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842883"
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