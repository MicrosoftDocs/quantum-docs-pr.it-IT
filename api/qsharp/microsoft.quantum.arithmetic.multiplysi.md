---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Operazione MultiplySI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719751"
---
# <a name="multiplysi-operation"></a>Operazione MultiplySI

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Moltiplica il valore intero `xs` con segno per intero con segno `ys` e archivia il risultato in `result` , che deve essere inizialmente zero.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

multiplicand a n bit (SignedLittleEndian)


### <a name="ys--signedlittleendian"></a>Ys: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

moltiplicatore n bit (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>risultato: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

il risultato a 2n bit (SignedLittleEndian) deve essere in stato inizialmente $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

