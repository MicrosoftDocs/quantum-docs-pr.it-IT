---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareUnitaryCoupledClusterState
title: Operazione PrepareUnitaryCoupledClusterState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareUnitaryCoupledClusterState
qsharp.summary: Unitary coupled-cluster state preparation of trial state
ms.openlocfilehash: 1d5b8963bd50752fef22fea0a3c002e3e2ebc90a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98836046"
---
# <a name="prepareunitarycoupledclusterstate-operation"></a><span data-ttu-id="84c2a-102">Operazione PrepareUnitaryCoupledClusterState</span><span class="sxs-lookup"><span data-stu-id="84c2a-102">PrepareUnitaryCoupledClusterState operation</span></span>

<span data-ttu-id="84c2a-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="84c2a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="84c2a-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="84c2a-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="84c2a-105">Accoppiato unitario-preparazione stato del cluster dello stato di valutazione</span><span class="sxs-lookup"><span data-stu-id="84c2a-105">Unitary coupled-cluster state preparation of trial state</span></span>

```qsharp
operation PrepareUnitaryCoupledClusterState (initialStatePreparation : (Qubit[] => Unit), clusterOperator : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], trotterStepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="84c2a-106">Input</span><span class="sxs-lookup"><span data-stu-id="84c2a-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="84c2a-107">initialStatePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="84c2a-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="84c2a-108">Unità per preparare lo stato di valutazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="84c2a-108">Unitary to prepare initial trial state.</span></span>


### <a name="clusteroperator--jordanwignerinputstate"></a><span data-ttu-id="84c2a-109">clusterOperator: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="84c2a-109">clusterOperator : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>




### <a name="trotterstepsize--double"></a><span data-ttu-id="84c2a-110">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="84c2a-110">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="84c2a-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="84c2a-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="84c2a-112">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="84c2a-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84c2a-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84c2a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

