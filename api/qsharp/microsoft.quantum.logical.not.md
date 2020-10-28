---
uid: Microsoft.Quantum.Logical.Not
title: Not-funzione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709862"
---
# <a name="not-function"></a>Not-funzione

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Restituisce la negazione booleana di un valore.

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a>Input

### <a name="value--bool"></a>valore: [bool](xref:microsoft.quantum.lang-ref.bool)

Valore da negare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `value` è `false` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let x = not value;
let x = Not(value);
```