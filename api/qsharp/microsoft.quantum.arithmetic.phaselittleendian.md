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
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="0bfe6-102">Tipo definito dall'utente PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="0bfe6-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="0bfe6-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="0bfe6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="0bfe6-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bfe6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bfe6-105">Interi senza segno little-endian in base a QFT.</span><span class="sxs-lookup"><span data-stu-id="0bfe6-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="0bfe6-106">Se, ad esempio, $ \ket{x} $ è la codifica little-endian del valore integer $x $ nella base di calcolo, $ \operatorname{QFTLE} \ket{x} $ è la codifica di $x $ nella base QFT.</span><span class="sxs-lookup"><span data-stu-id="0bfe6-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="0bfe6-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="0bfe6-107">Remarks</span></span>

<span data-ttu-id="0bfe6-108">Si abbrevia `PhaseLittleEndian` come `PhaseLE` nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="0bfe6-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bfe6-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bfe6-109">See Also</span></span>

- [<span data-ttu-id="0bfe6-110">Microsoft. Quantum. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="0bfe6-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="0bfe6-111">Microsoft. Quantum. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="0bfe6-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)