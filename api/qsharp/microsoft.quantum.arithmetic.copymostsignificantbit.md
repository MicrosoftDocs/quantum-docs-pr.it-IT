---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operazione CopyMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721215"
---
# <a name="copymostsignificantbit-operation"></a>Operazione CopyMostSignificantBit

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Copia il bit più significativo di un registro qubit `from` che rappresenta un Unsigned Integer in qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="from--littleendian"></a>da: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Unsigned Integer dal quale viene copiato il bit più alto.
il numero intero è codificato in formato little-endian.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit in cui viene copiato il bit più alto. La codifica di bit è in base al calcolo.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)