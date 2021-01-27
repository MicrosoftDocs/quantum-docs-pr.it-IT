---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Tipo definito dall'utente PhaseLittleEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842992"
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