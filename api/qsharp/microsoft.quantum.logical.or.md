---
uid: Microsoft.Quantum.Logical.Or
title: Funzione or
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719979"
---
# <a name="or-function"></a>Funzione or

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Restituisce la disgiunzione booleana di due valori.

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Input

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)

Primo valore da considerare.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Secondo valore da considerare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` o `b` sono `true` .

## <a name="remarks"></a>Commenti

A differenza dell' `or` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.

Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:

```Q#
let x = a or b;
let x = Or(a, b);
```