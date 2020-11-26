---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 2d0b50bd2467fc01caacbbcb22f98c59a2d13922
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201224"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="838d5-102">BitFlipCode (funzione)</span><span class="sxs-lookup"><span data-stu-id="838d5-102">BitFlipCode function</span></span>

<span data-ttu-id="838d5-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="838d5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="838d5-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="838d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="838d5-105">Restituisce un valore QECC che rappresenta il codificatore di codice ⟦ 3, 1, 1 ⟧ bit flip e il decodificatore con misurazione della sindrome sul posto.</span><span class="sxs-lookup"><span data-stu-id="838d5-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="838d5-106">Output: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="838d5-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="838d5-107">Restituisce un'implementazione di un codice di correzione degli errori Quantum specificando un `QECC` tipo.</span><span class="sxs-lookup"><span data-stu-id="838d5-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>