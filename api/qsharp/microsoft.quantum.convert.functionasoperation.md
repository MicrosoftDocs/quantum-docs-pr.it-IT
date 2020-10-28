---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713513"
---
# <a name="functionasoperation-function"></a>FunctionAsOperation (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


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