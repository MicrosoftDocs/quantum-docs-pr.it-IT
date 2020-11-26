---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 35dc76a06fd4e8c819b785fd4c588f108c918326
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205780"
---
# <a name="operationpowa-function"></a>OperationPowA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Genera un'operazione a potenza.
Il modificatore `A` indica che l'operazione è adjointable.

Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a>Input

### <a name="op--t--unit--is-adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Un'operazione $U $ che rappresenta il Gate da ripetere.


### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di volte in cui $U $ deve essere ripetuto.



## <a name="output--t--unit--is-adj"></a>Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ

Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di operazione da alimentare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)