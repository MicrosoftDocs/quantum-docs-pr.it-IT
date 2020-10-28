---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716414"
---
# <a name="controlledonint-function"></a>ControlledOnInt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Restituisce un operatore unitario che applica un oggetto Oracle nel registro di destinazione se lo stato del registro di controllo corrisponde a un numero intero positivo specificato.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Numero intero positivo.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operatore unitario.



## <a name="output--qubitt--unit-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],' t) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operatore unitario che si applica al `oracle` Registro di destinazione se lo stato del registro di controllo corrisponde allo stato numerico `numberState` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Il valore di `numberState` viene interpretato utilizzando una codifica little-endian.