---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operazione MeasureInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843112"
---
# <a name="measureinteger-operation"></a>Operazione MeasureInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Misura il contenuto di un registro Quantum e lo converte in un numero intero. La misurazione viene eseguita rispetto alla base di calcolo standard, ovvero eigenbasis di `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Input

### <a name="target--littleendian"></a>destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro Quantum nella codifica little-endian.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Unsigned Integer che contiene il valore misurato di `target` .

## <a name="remarks"></a>Commenti

Questa operazione Reimposta il registro di input sullo stato $ \ket{00\cdots 0} $, adatto per il rilascio di nuovo in un computer di destinazione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)