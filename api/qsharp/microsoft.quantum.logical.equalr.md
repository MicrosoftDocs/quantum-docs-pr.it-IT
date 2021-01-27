---
uid: Microsoft.Quantum.Logical.EqualR
title: Equalr (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815992"
---
# <a name="equalr-function"></a>Equalr (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce true se e solo se due input sono uguali.

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Input

### <a name="a--__invalidresult__"></a>r: __non <Result> valido__

Primo valore da confrontare.


### <a name="b--__invalidresult__"></a>b: __non <Result> valida__

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` è uguale a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```