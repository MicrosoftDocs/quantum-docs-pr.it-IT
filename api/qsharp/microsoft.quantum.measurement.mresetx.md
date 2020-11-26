---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operazione MResetX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 04fb0f84ddf79a3d2cfc21fdaabd16c129f6d72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194203"
---
# <a name="mresetx-operation"></a><span data-ttu-id="9ae95-102">Operazione MResetX</span><span class="sxs-lookup"><span data-stu-id="9ae95-102">MResetX operation</span></span>

<span data-ttu-id="9ae95-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="9ae95-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="9ae95-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9ae95-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9ae95-105">Misura un singolo qubit in base X e lo reimposta su uno stato iniziale fisso dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="9ae95-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="9ae95-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ae95-106">Description</span></span>

<span data-ttu-id="9ae95-107">Esegue una misurazione a qubit singolo in $X $-base e garantisce che qubit venga restituito a $ \ket {0} $ dopo la misurazione.</span><span class="sxs-lookup"><span data-stu-id="9ae95-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="9ae95-108">Input</span><span class="sxs-lookup"><span data-stu-id="9ae95-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="9ae95-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9ae95-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9ae95-110">Singolo qubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="9ae95-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9ae95-111">Output: __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="9ae95-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="9ae95-112">Risultato della misurazione `target` in Pauli $X $ base.</span><span class="sxs-lookup"><span data-stu-id="9ae95-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>