---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198028"
---
# <a name="greaterthand-function"></a>GreaterThanD (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce true se e solo se un numero è maggiore di un altro numero.

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Input

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

Primo valore da confrontare.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` è strettamente maggiore di `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```