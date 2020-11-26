---
uid: Microsoft.Quantum.Convert.Call
title: Operazione di chiamata
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214212"
---
# <a name="call-operation"></a>Operazione di chiamata

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Chiama una funzione con un input specificato.

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a>Descrizione

Data una funzione e un input per tale funzione, chiama la funzione e ne restituisce l'output.

## <a name="input"></a>Input

### <a name="fn--input---output"></a>FN: output ' input->'

Funzione da chiamare.


### <a name="input--input"></a>input:' input

Input da passare alla funzione.



## <a name="output--output"></a>Output:' output

Risultato della chiamata a `fn`.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="input"></a>' Input


### <a name="output"></a>' Output



## <a name="remarks"></a>Commenti

Questa operazione è particolarmente utile per forzare la chiamata di una funzione in una posizione specifica all'interno di un'operazione o per chiamare una funzione in cui è prevista un'operazione.