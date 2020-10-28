---
uid: Microsoft.Quantum.Logical.Conditioned
title: Funzione conditioned
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720786"
---
# <a name="conditioned-function"></a>Funzione conditioned

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Restituisce uno di due valori, a seconda del valore di una condizione booleana.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Input

### <a name="condition--bool"></a>condizione: [bool](xref:microsoft.quantum.lang-ref.bool)

Condizione utilizzata per controllare quale input viene restituito.


### <a name="iftrue--t"></a>ifTrue: t

Valore da restituire quando `condition` è `true` .


### <a name="iffalse--t"></a>ifFalse: t

Valore da restituire quando `condition` è `false` .



## <a name="output--t"></a>Output:' t

`ifTrue` Se `condition` è `true` e `ifFalse` in caso contrario.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

A differenza dell' `?|` operatore, questa funzione non è a corto circuito, in modo che entrambi gli input siano valutati completamente.

Fino a un comportamento di corto circuito, gli elementi seguenti sono equivalenti:

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```