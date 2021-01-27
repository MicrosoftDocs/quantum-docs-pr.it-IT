---
uid: Microsoft.Quantum.Logical.EqualI
title: Equali (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816742"
---
# <a name="equali-function"></a>Equali (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce true se e solo se due input sono uguali.

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Primo valore da confrontare.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` è uguale a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```