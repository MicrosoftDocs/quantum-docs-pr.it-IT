---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 40f059e49affbb1b5af7dc349f6ee53dfb357873
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197739"
---
# <a name="lessthand-function"></a>LessThanD (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce true se e solo se un numero è minore di un altro numero.

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Input

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

Primo valore da confrontare.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` è strettamente inferiore a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```