---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Funzione partizionata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220502"
---
# <a name="partitioned-function"></a>Funzione partizionata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Suddivide una matrice in più parti.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Input

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)[]

Numero di elementi in ogni parte della matrice


### <a name="arr--t"></a>arr:' t []

Matrice di input da suddividere.



## <a name="output--t"></a>Output:' t [] []

Più matrici in cui la prima matrice è la prima `nElements[0]` di `arr` e la seconda matrice è la successiva `nElements[1]` di e `arr` così via. L'ultima matrice conterrà tutti gli elementi rimanenti.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

