---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 98fa55c249f2ade414254d1bccda46a8602b828c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815857"
---
# <a name="greaterthanorequald-function"></a>GreaterThanOrEqualD (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce true se e solo se un numero è maggiore o uguale a un altro numero.

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Input

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

Primo valore da confrontare.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` è maggiore di o è uguale a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```