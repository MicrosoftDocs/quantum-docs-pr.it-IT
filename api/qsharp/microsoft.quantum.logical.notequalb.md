---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814418"
---
# <a name="notequalb-function"></a>NotEqualB (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```