---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Operazione AddI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721686"
---
# <a name="addi-operation"></a>Operazione AddI

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Sceglie automaticamente tra l'aggiunta con Carry e senza, a seconda delle dimensioni del registro `ys` .

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit Addend.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

ADDEND con almeno $n $ qubits. Manterrà il risultato.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

