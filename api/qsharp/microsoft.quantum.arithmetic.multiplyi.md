---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operazione multiplyi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719763"
---
# <a name="multiplyi-operation"></a>Operazione multiplyi

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Moltiplica integer `xs` per intero `ys` e archivia il risultato in `result` , che deve essere inizialmente zero.

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit multiplicand (LittleEndian)


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

moltiplicatore $n $ bit (LittleEndian)


### <a name="result--littleendian"></a>risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

il risultato $2n $-bit (LittleEndian) deve essere in stato inizialmente $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Usa un approccio standard di spostamento e aggiunta per implementare la moltiplicazione.
La versione controllata è stata migliorata copiando $x _i $ in un ancilla qubit condizionato sul qubits di controllo e quindi controllando l'aggiunta in ancilla qubit.