---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Operazione ApplyPauliFromBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: 09754accb92c1339b781003e5722e3c8f5884e6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717811"
---
# <a name="applypaulifrombitstring-operation"></a>Operazione ApplyPauliFromBitString

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applica un operatore Pauli in ogni qubit in una matrice se il bit corrispondente di una matrice booleana corrisponde a un input specificato.

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operatore Pauli da applicare a `qubits[idx]` where `bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>in una delle seguenti operazioni: [bool](xref:microsoft.quantum.lang-ref.bool)

applica Pauli se bit è questo valore


### <a name="bits--bool"></a>BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Registro booleano che specifica quale qubit corrispondente in `qubits` deve essere utilizzato


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro Quantum su cui applicare in modo selettivo l'operatore Pauli specificato



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

La matrice booleana e il registro Quantum devono essere di uguale lunghezza.