---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715672"
---
# <a name="operationpowca-function"></a>OperationPowCA (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Genera un'operazione a potenza.
Il modificatore `A` indica che l'operazione è controllabile e adjointable.

Ovvero, data un'operazione che rappresenta un controllo $U $, restituisce una nuova operazione $U ^ m $ per una potenza $m $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Input

### <a name="op--t--unit-ctl--adj"></a>op:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Un'operazione $U $ che rappresenta il Gate da ripetere.


### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)

Il numero di volte in cui $U $ deve essere ripetuto.



## <a name="output--t--unit-ctl--adj"></a>Output:' t => [unità](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ

Nuova operazione che rappresenta $U ^ m $, dove $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di operazione da alimentare.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)