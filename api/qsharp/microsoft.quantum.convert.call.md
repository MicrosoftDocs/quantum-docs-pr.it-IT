---
uid: Microsoft.Quantum.Convert.Call
title: Operazione di chiamata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850204"
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