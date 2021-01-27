---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Operazione MultiplySI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7c7e7dfaee9b9dc717db44956506984e60281dd2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843009"
---
# <a name="multiplysi-operation"></a>Operazione MultiplySI

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Moltiplica il valore intero `xs` con segno per intero con segno `ys` e archivia il risultato in `result` , che deve essere inizialmente zero.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

multiplicand a n bit (SignedLittleEndian)


### <a name="ys--signedlittleendian"></a>Ys: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

moltiplicatore n bit (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>risultato: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

il risultato a 2n bit (SignedLittleEndian) deve essere in stato inizialmente $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

