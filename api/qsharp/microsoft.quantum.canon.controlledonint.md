---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840795"
---
# <a name="controlledonint-function"></a>ControlledOnInt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un operatore unitario che applica un oggetto Oracle nel registro di destinazione se lo stato del registro di controllo corrisponde a un numero intero positivo specificato.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Numero intero positivo.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operatore unitario.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operatore unitario che si applica al `oracle` Registro di destinazione se lo stato del registro di controllo corrisponde allo stato numerico `numberState` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Il valore di `numberState` viene interpretato utilizzando una codifica little-endian.