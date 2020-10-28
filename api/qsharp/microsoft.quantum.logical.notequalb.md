---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709834"
---
# <a name="notequalb-function"></a>NotEqualB (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Restituisce true se e solo se due input non sono uguali.

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Input

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)

Primo valore da confrontare.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` non è uguale a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```