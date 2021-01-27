---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 4f4631bb49f769816a3df772f7b2f346c8ccfc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842868"
---
# <a name="columnatunchecked-function"></a>ColumnAtUnchecked (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

