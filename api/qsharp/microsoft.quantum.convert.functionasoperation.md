---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224378"
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