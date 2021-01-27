---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operazione CopyMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843275"
---
# <a name="copymostsignificantbit-operation"></a>Operazione CopyMostSignificantBit

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Copia il bit più significativo di un registro qubit `from` che rappresenta un Unsigned Integer in qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
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