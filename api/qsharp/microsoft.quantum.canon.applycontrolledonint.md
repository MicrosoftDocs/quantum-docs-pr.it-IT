---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operazione ApplyControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718350"
---
# <a name="applycontrolledonint-operation"></a>Operazione ApplyControlledOnInt

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione unitaria nel registro di destinazione se lo stato del registro di controllo corrisponde a un numero intero positivo specificato.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Input

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Intero non negativo in cui `oracle` deve essere controllata l'operazione.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione unitaria da controllare.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro Quantum che controlla l'applicazione di `oracle` .


### <a name="targetregister--t"></a>targetRegister: t

Registro su cui applicare `oracle` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Il valore di `numberState` viene interpretato utilizzando una codifica little-endian.

`numberState` deve essere al massimo $2 ^ \texttt{Length (controlRegister)}-$1.
Ad esempio, `numberState = 537` indica che `oracle` viene applicato se e solo se `controlRegister` è nello stato $ \ket {537} $.