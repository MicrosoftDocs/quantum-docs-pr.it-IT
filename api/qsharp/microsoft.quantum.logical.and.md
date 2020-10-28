---
uid: Microsoft.Quantum.Logical.And
title: And (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720798"
---
# <a name="and-function"></a>And (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Restituisce la congiunzione booleana di due valori.

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>Input

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)

Primo valore da considerare.


### <a name="b--bool"></a>b: [bool](xref:microsoft.quantum.lang-ref.bool)

Secondo valore da considerare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` e `b` sono entrambi `true` .

## <a name="remarks"></a>Commenti

A differenza dell' `and` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.

Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:

```Q#
let x = a and b;
let x = And(a, b);
```