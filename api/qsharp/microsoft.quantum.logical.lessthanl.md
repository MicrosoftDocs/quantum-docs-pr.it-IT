---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709957"
---
# <a name="lessthanl-function"></a>LessThanL (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Restituisce true se e solo se un numero è minore di un altro numero.

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Input

### <a name="a--bigint"></a>r: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Primo valore da confrontare.


### <a name="b--bigint"></a>b: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` è strettamente inferiore a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```