---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719451"
---
# <a name="columnatunchecked-function"></a>ColumnAtUnchecked (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Questa funzione non controlla la forma matrice

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Descrizione

Questa funzione può essere utilizzata in altre funzioni multidimensionali che controllano già la matrice di input per una forma rettangolare valida.

## <a name="input"></a>Input

### <a name="column--int"></a>colonna: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="matrix--t"></a>matrice:' t [] []





## <a name="output--t"></a>Output:' t []



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

