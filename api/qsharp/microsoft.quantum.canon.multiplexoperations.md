---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Operazione MultiplexOperations
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad66b39fcfacbe5231ec3b9ba96989d6d5d449c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206103"
---
# <a name="multiplexoperations-operation"></a>Operazione MultiplexOperations

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica una matrice di operazioni controllate da una matrice di stati numerici.

Ovvero applica un'operazione unitaria controllata da moltiplicazione $U $ che applica una $V unitaria _j $ se controllata dal $n $-qubit numero stato $ \ket{j} $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="unitaries--t--unit--is-adj--ctl"></a>unitaries:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL []

Matrice di un massimo di $2 ^ n $ operazioni unitarie. L'operazione $j $ th viene indicizzata in base al numero di stato $ \ket{j} $ codificato in formato little-endian.


### <a name="index--littleendian"></a>Indice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n il registro di controllo $-qubit che codifica gli Stati numerici $ \ket{j} $ in formato little-endian.


### <a name="target--t"></a>destinazione:' t

Registro qubit generico su cui $V _j $ agisce.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

`coefficients` verranno riempiti con gli elementi Identity se sono specificati meno di $2 ^ n $. Questa implementazione USA qubits ausiliari $n-$1.

## <a name="references"></a>Riferimenti

- Verso la prima simulazione quantistica con aumento della velocità di Quantum Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan su https://arxiv.org/abs/1711.10980