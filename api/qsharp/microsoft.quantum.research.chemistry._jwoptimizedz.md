---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: Operazione _JWOptimizedZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: e0b442a7ac237525acdc80e8e79044ebb523f8a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225908"
---
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="c7f28-102">Operazione _JWOptimizedZ</span><span class="sxs-lookup"><span data-stu-id="c7f28-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="c7f28-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c7f28-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c7f28-104">Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c7f28-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="c7f28-105">Applica una rotazione RZ, con un trucco C-NOT alla fase doppia nella stima della fase.</span><span class="sxs-lookup"><span data-stu-id="c7f28-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c7f28-106">Input</span><span class="sxs-lookup"><span data-stu-id="c7f28-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="c7f28-107">angolo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c7f28-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c7f28-108">Angolo di rotazione RZ.</span><span class="sxs-lookup"><span data-stu-id="c7f28-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="c7f28-109">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c7f28-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c7f28-110">Qubit che determina il segno di evoluzione del tempo.</span><span class="sxs-lookup"><span data-stu-id="c7f28-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c7f28-111">Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c7f28-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="c7f28-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7f28-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

