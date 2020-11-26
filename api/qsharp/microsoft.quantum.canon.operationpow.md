---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 808001200d276ca21cc5a70140d5d84d96da3496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205814"
---
# <a name="operationpow-function"></a>OperationPow (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genera un'operazione a potenza.

Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>Input

### <a name="op--t--unit"></a>op:' t = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Un'operazione $U $ che rappresenta il Gate da ripetere.


### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di volte in cui $U $ deve essere ripetuto.



## <a name="output--t--unit"></a>Output:' t = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di operazione da alimentare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft. Quantum. Canon. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft. Quantum. Canon. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)