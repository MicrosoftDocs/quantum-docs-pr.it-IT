---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Operazione PrepareEntangledState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854371"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="ebe46-102">Operazione PrepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="ebe46-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="ebe46-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ebe46-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ebe46-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebe46-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebe46-105">Pairwise si impiglia in due registri qubit.</span><span class="sxs-lookup"><span data-stu-id="ebe46-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="ebe46-106">Ovvero, dati due registri, prepara lo stato {1} di \frac {\sqrt {2} } \left (\ket {00} + \ket {11} \right) di ogni coppia di qubits sui rispettivi registri, supponendo che ogni registro venga avviato nello stato $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="ebe46-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ebe46-107">Input</span><span class="sxs-lookup"><span data-stu-id="ebe46-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="ebe46-108">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ebe46-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ebe46-109">Matrice qubit nello stato $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="ebe46-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="ebe46-110">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ebe46-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ebe46-111">Matrice qubit nello stato $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="ebe46-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebe46-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebe46-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

