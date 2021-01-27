---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Operazione MultiplexOperations
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 1cf483bb0d3b7cc43d271b65a2363fab95ff0f3b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852537"
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