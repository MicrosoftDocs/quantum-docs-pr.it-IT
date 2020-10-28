---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709792"
---
# <a name="notequalr-function"></a>NotEqualR (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Restituisce true se e solo se due input non sono uguali.

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a>Input

### <a name="a--__invalidresult__"></a>r: __non <Result> valido__

Primo valore da confrontare.


### <a name="b--__invalidresult__"></a>b: __non <Result> valida__

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` non è uguale a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```