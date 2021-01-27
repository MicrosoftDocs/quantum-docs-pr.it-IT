---
uid: Microsoft.Quantum.Logical.Conditioned
title: Funzione conditioned
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817295"
---
# <a name="conditioned-function"></a>Funzione conditioned

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```