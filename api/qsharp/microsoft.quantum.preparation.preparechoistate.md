---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Operazione PrepareChoiState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210574"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="0e41c-102">Operazione PrepareChoiState</span><span class="sxs-lookup"><span data-stu-id="0e41c-102">PrepareChoiState operation</span></span>

<span data-ttu-id="0e41c-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="0e41c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="0e41c-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e41c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e41c-105">Prepara lo stato Choi-Jamiołkowski per una determinata operazione sui registri di riferimento e di destinazione specificati.</span><span class="sxs-lookup"><span data-stu-id="0e41c-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0e41c-106">Input</span><span class="sxs-lookup"><span data-stu-id="0e41c-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="0e41c-107">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="0e41c-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0e41c-108">Operazione $ \Lambda $ la cui proprietà Choi – Jamiołkowski state $J (\Lambda)/2 ^ N $ deve essere preparata, dove $N $ è il numero di qubits su cui `op` agisce.</span><span class="sxs-lookup"><span data-stu-id="0e41c-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="0e41c-109">riferimento: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e41c-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e41c-110">Un registro di qubits che inizia nello stato $ \ket{00\cdots 0} $ da usare come riferimento per l'azione di `op` .</span><span class="sxs-lookup"><span data-stu-id="0e41c-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0e41c-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e41c-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e41c-112">Un registro di qubits inizialmente nello stato $ \ket{00\cdots 0} $ in cui deve `op` essere applicato.</span><span class="sxs-lookup"><span data-stu-id="0e41c-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e41c-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e41c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0e41c-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="0e41c-114">Remarks</span></span>

<span data-ttu-id="0e41c-115">Il $J di stato Choi-Jamiłkowski (\Lambda) $ di un processo quantum è definito come $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ where $ | X\rangle \! \rangle $ è la *vettorizzazione* di una matrice $X $ nella convenzione di stack di colonne.</span><span class="sxs-lookup"><span data-stu-id="0e41c-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="0e41c-116">L'apprendimento di una descrizione classica di questo stato fornisce informazioni complete sull'effetto di $ \Lambda $ che agisce sugli stati di input arbitrari e costituisce la base della *tomografia del processo quantum*.</span><span class="sxs-lookup"><span data-stu-id="0e41c-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e41c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e41c-117">See Also</span></span>

- [<span data-ttu-id="0e41c-118">Microsoft. Quantum. preping. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="0e41c-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="0e41c-119">Microsoft. Quantum. preping. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="0e41c-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="0e41c-120">Microsoft. Quantum. preping. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="0e41c-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)