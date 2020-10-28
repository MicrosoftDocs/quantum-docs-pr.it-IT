---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operazione ApplyControlledOnBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718359"
---
# <a name="applycontrolledonbitstring-operation"></a>Operazione ApplyControlledOnBitString

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione unitaria nel registro di destinazione, controllata su uno stato specificato da una maschera di bit specificata.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Input

### <a name="bits--bool"></a>BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Stringa di bit per controllare l'operazione unitaria specificata su.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione unitaria da applicare al registro di destinazione.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro Quantum che controlla l'applicazione di `oracle` .


### <a name="targetregister--t"></a>targetRegister: t

Registro di destinazione da passare a `oracle` come input.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Il modello fornito da `bits` può essere più breve di `controlRegister` , nel qual caso i qubits di controllo aggiuntivi vengono ignorati, ovvero non sono controllati in $ \ket {0} $ né $ \ket {1} $.
Se `bits` è più lungo di `controlRegister` , viene generato un errore.

Ad esempio, `bits = [0,1,0,0,1]` indica che `oracle` viene applicato se e solo se `controlRegister` è nello stato $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.