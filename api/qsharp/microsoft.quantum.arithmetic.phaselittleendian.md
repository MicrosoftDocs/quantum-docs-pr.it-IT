---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Tipo definito dall'utente PhaseLittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222423"
---
# <a name="phaselittleendian-user-defined-type"></a>Tipo definito dall'utente PhaseLittleEndian

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Interi senza segno little-endian in base a QFT.

Se, ad esempio, $ \ket{x} $ è la codifica little-endian del valore integer $x $ nella base di calcolo, $ \operatorname{QFTLE} \ket{x} $ è la codifica di $x $ nella base QFT.

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Commenti

Si abbrevia `PhaseLittleEndian` come `PhaseLE` nella documentazione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Microsoft. Quantum. Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)