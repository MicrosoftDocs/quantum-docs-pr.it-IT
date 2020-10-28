---
uid: Microsoft.Quantum.Arrays.Merged
title: Funzione unita
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719010"
---
# <a name="merged-function"></a>Funzione unita

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Date due matrici ordinate, restituisce una singola matrice contenente gli elementi di entrambi gli elementi in ordine ordinato. Utilizzato internamente dall'ordinamento di tipo merge.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="comparison--tt---bool"></a>confronto: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>Left:' t []




### <a name="right--t"></a>a destra:' t []





## <a name="output--t"></a>Output:' t []



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

