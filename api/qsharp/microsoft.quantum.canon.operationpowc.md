---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715686"
---
# <a name="operationpowc-function"></a>OperationPowC (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Genera un'operazione a potenza.
Il modificatore `C` indica che l'operazione è controllabile.

Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Input

### <a name="op--t--unit-ctl"></a>op:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Un'operazione $U $ che rappresenta il Gate da ripetere.


### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di volte in cui $U $ deve essere ripetuto.



## <a name="output--t--unit-ctl"></a>Output:' t => CTL [unit](xref:microsoft.quantum.lang-ref.unit)

Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di operazione da alimentare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)