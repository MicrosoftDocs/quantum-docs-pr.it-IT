---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713600"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


Data una stringa di bit, restituisce un operatore Pauli multiqubit rappresentato come una matrice di operatori Pauli a qubit singolo.

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>Input

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operatore Pauli da applicare a qubits dove `bitsApply == bits[idx]` .


### <a name="bitapply--bool"></a>in una delle seguenti operazioni: [bool](xref:microsoft.quantum.lang-ref.bool)

applicare Pauli se bit è questo valore.


### <a name="bits--bool"></a>BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Matrice booleana.



## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>Commenti

La matrice booleana e il registro Quantum devono essere di uguale lunghezza.