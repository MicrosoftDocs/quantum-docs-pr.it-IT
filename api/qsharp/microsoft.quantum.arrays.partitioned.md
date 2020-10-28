---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Funzione partizionata
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718974"
---
# <a name="partitioned-function"></a>Funzione partizionata

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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

