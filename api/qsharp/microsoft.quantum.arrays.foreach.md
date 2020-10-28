---
uid: Microsoft.Quantum.Arrays.ForEach
title: Operazione ForEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719202"
---
# <a name="foreach-operation"></a>Operazione ForEach

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Data una matrice e un'operazione definita per gli elementi della matrice, restituisce una nuova matrice costituita dalle immagini della matrice originale sotto l'operazione.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Input

### <a name="action--t--u"></a>azione:' t =>' U 

Operazione da `'T` a `'U` applicata a ogni elemento.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--u"></a>Output:' U []

Matrice `'U[]` di elementi mappati dall' `action` operazione.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.
### <a name="u"></a>' U

Tipo di risultato dell' `action` operazione.

## <a name="remarks"></a>Commenti

L'operazione è definita per i tipi generici, ad esempio ogni volta che è presente una matrice `'T[]` e un'operazione è `action : 'T -> 'U` possibile eseguire il mapping degli elementi della matrice e produrre una nuova matrice di tipo `'U[]` .