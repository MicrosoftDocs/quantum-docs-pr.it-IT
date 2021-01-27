---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815947"
---
# <a name="greaterthani-function"></a>GreaterThanI (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce true se e solo se un numero è maggiore di un altro numero.

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Primo valore da confrontare.


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` è strettamente maggiore di `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```