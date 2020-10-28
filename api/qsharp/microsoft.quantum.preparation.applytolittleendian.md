---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Operazione ApplyToLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: d94a9969a3f827d594946ab8ca6cd4672da7ef7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724104"
---
# <a name="applytolittleendian-operation"></a>Operazione ApplyToLittleEndian

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione ai qubits sottostanti che costituiscono un registro little-endian. Questa operazione è contrassegnata come interna, perché un registro Little-Endian è pensato come "opaco", in modo che questo sia solo un dettaglio di implementazione.

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="bareop--qubit--unit-adj--ctl"></a>bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL




### <a name="register--littleendian"></a>registra: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

