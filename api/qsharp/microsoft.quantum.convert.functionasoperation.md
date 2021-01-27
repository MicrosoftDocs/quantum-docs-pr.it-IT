---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833830"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte le funzioni in operazioni.

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a>Descrizione

Data una funzione, restituisce un'operazione che chiama tale funzione e che non esegue altre operazioni.

## <a name="input"></a>Input

### <a name="fn--input---output"></a>FN: output ' input->'

Funzione da convertire in un'operazione.



## <a name="output--input--output"></a>Output: output ' input =>' 

Operazione `op` analoga `op(input)` a `fn(input)` per tutti `input` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="input"></a>' Input

Tipo di input della funzione da convertire.
### <a name="output"></a>' Output

Tipo di output della funzione da convertire.

## <a name="remarks"></a>Commenti

Questo è particolarmente utile per passare funzioni a funzioni o operazioni che prevedono un'operazione come input.