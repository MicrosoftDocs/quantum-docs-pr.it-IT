---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Operazione PrepareSparseMultiConfigurationalState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 4d39be70c48ed49a1eec410ed6f8e5081dc1e8ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224769"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="cfe22-102">Operazione PrepareSparseMultiConfigurationalState</span><span class="sxs-lookup"><span data-stu-id="cfe22-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="cfe22-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="cfe22-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="cfe22-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cfe22-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="cfe22-105">Preparazione dello stato di valutazione a più configurazioni di tipo sparse tramite l'aggiunta di eccitazioni allo stato di valutazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="cfe22-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cfe22-106">Input</span><span class="sxs-lookup"><span data-stu-id="cfe22-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="cfe22-107">initialStatePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="cfe22-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cfe22-108">Unità per preparare lo stato di valutazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="cfe22-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="cfe22-109">eccitazioni: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="cfe22-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="cfe22-110">Eccitazioni dello stato iniziale della versione di valutazione rappresentate dall'ampiezza dell'eccitazione e dagli indici qubit dell'eccitazione.</span><span class="sxs-lookup"><span data-stu-id="cfe22-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cfe22-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cfe22-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cfe22-112">Qubits di hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="cfe22-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cfe22-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfe22-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

