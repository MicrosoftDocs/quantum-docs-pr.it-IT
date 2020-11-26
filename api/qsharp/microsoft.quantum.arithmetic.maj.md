---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operazione MAJ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222763"
---
# <a name="maj-operation"></a><span data-ttu-id="db944-102">Operazione MAJ</span><span class="sxs-lookup"><span data-stu-id="db944-102">MAJ operation</span></span>

<span data-ttu-id="db944-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="db944-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="db944-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db944-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db944-105">Questa operazione applica la maggioranza sul posto a 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="db944-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="db944-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db944-106">Description</span></span>

<span data-ttu-id="db944-107">Se si denota lo stato della qubit di destinazione come $ \ket{z} $ e gli Stati di input del qubits di input come $ \ket{x} $ e $ \ket{y} $, questa operazione esegue la trasformazione seguente: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="db944-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="db944-108">Input</span><span class="sxs-lookup"><span data-stu-id="db944-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="db944-109">input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="db944-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="db944-110">Primo qubit di input.</span><span class="sxs-lookup"><span data-stu-id="db944-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="db944-111">INPUT1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="db944-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="db944-112">Secondo qubit di input.</span><span class="sxs-lookup"><span data-stu-id="db944-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="db944-113">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="db944-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="db944-114">Qubit su cui verrà applicata la funzione di maggioranza.</span><span class="sxs-lookup"><span data-stu-id="db944-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db944-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db944-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

