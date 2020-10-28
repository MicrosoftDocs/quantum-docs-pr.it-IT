---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definito dall'utente ReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724213"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="b747f-102">Tipo definito dall'utente ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="b747f-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="b747f-103">Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="b747f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="b747f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b747f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b747f-105">Rappresenta un oggetto Oracle di Reflection.</span><span class="sxs-lookup"><span data-stu-id="b747f-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="b747f-106">Una reflection Oracle, $O $, contiene input:</span><span class="sxs-lookup"><span data-stu-id="b747f-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="b747f-107">Fase $ \Phi $ in base alla quale ruotare il sottospazio riflesso.</span><span class="sxs-lookup"><span data-stu-id="b747f-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="b747f-108">Registro qubit in cui eseguire la reflection specificata.</span><span class="sxs-lookup"><span data-stu-id="b747f-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="b747f-109">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="b747f-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="b747f-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="b747f-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="b747f-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="b747f-111">Remarks</span></span>

<span data-ttu-id="b747f-112">Questo $O Oracle = \boldone-(1-e ^ {i \Phi}) \ket{\psi}\bra{\psi} $ esegue una reflection parziale di una fase $ \Phi $ relativa a un singolo stato puro $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="b747f-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>