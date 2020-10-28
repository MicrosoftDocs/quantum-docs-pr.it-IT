---
uid: Microsoft.Quantum.Canon.Delay
title: Operazione Delay
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716316"
---
# <a name="delay-operation"></a>Operazione Delay

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica una determinata operazione con un ritardo.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Descrizione

Data un'operazione e un input per tale operazione, applica l'operazione dopo che è stato fornito un input aggiuntivo.
In particolare, l'espressione `Delay(op, arg, _)` è un'operazione che si applica `op` a `arg` quando viene chiamato.
Expression `Delay(op,arg,_)` consente di ritardare l'applicazione di `op` .

## <a name="input"></a>Input

### <a name="op--t--u"></a>op:' t =>' U 

Operazione da applicare.


### <a name="arg--t"></a>ARG:' t

Input a cui viene applicata l'operazione.


### <a name="aux--unit"></a>Aux: [unità](xref:microsoft.quantum.lang-ref.unit)

Argomento utilizzato per ritardare l'applicazione dell'operazione utilizzando l'applicazione parziale.



## <a name="output--u"></a>Output:' U



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input dell'operazione da ritardare.
### <a name="u"></a>' U

Tipo restituito dell'operazione da ritardare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft. Quantum. Canon. Delaya](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft. Quantum. Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft. Quantum. Canon. Delayed](xref:Microsoft.Quantum.Canon.Delayed)