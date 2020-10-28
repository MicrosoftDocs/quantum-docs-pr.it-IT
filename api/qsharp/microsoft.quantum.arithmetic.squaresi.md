---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: Operazione Squares
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719535"
---
# <a name="squaresi-operation"></a>Operazione Squares

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Un intero con segno quadrato `xs` e archivia il risultato in `result` , che deve essere inizialmente zero.

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

da n bit intero a quadrato (SignedLittleEndian)


### <a name="result--signedlittleendian"></a>risultato: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

il risultato a 2n bit (SignedLittleEndian) deve essere in stato inizialmente $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

L'implementazione si basa su IntegerSquare.