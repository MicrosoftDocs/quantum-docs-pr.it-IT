---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operazione MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720966"
---
# <a name="measureinteger-operation"></a>Operazione MeasureInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


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