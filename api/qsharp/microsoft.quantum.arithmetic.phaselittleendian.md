---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Tipo definito dall'utente PhaseLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719730"
---
# <a name="phaselittleendian-user-defined-type"></a>Tipo definito dall'utente PhaseLittleEndian

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


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