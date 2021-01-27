---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 38f30309a4c27a5ef7e112a09a0efe3b5512d4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849040"
---
# <a name="notequald-function"></a>NotEqualD (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce true se e solo se due input non sono uguali.

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Input

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

Primo valore da confrontare.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` non è uguale a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
let cond = a != b;
let cond = NotEqualD(a, b);
```