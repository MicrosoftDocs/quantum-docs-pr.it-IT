---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846167"
---
# <a name="emptyarray-function"></a>EmptyArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Restituisce la matrice vuota di un tipo specificato.

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>Output:' TElement []

Matrice vuota.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="telement"></a>' TElement

Tipo di elementi della matrice.

## <a name="example"></a>Esempio

```qsharp
let empty = EmptyArray<Int>();
```