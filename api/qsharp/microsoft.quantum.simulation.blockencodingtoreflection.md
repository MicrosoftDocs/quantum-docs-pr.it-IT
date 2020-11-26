---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225347"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte un oggetto `BlockEncoding` in un oggetto equivalente `BLockEncodingReflection` .

In altri casi, dato un `BlockEncoding` unity $U $ che codifica un operatore $H $ di interesse, lo converte in un `BlockEncodingReflection` $U ' $ che codifica lo stesso operatore, ma soddisfa anche $U ' ^ \Dagger = U ' $.
Questo aumenta le dimensioni del registro ausiliario di $U $ di un qubit.

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Input

### <a name="blockencoding--blockencoding"></a>blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

`BlockEncoding`Unitario $U $ da convertire in una reflection.



## <a name="output--blockencodingreflection"></a>Output: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Un $U unitario ' $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e soddisfa $U ' ^ \Dagger = U ' $.

## <a name="remarks"></a>Commenti

Questo aumenta le dimensioni del registro ausiliario di $U $ di un qubit.

## <a name="references"></a>Riferimenti

- Simulazione Hamiltoniana di Qubitization Guang Hao low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)