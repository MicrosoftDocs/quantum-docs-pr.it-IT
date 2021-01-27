---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operazione MAJ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846556"
---
# <a name="maj-operation"></a><span data-ttu-id="32eea-102">Operazione MAJ</span><span class="sxs-lookup"><span data-stu-id="32eea-102">MAJ operation</span></span>

<span data-ttu-id="32eea-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="32eea-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="32eea-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32eea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32eea-105">Questa operazione applica la maggioranza sul posto a 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="32eea-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="32eea-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32eea-106">Description</span></span>

<span data-ttu-id="32eea-107">Se si denota lo stato della qubit di destinazione come $ \ket{z} $ e gli Stati di input del qubits di input come $ \ket{x} $ e $ \ket{y} $, questa operazione esegue la trasformazione seguente: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="32eea-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="32eea-108">Input</span><span class="sxs-lookup"><span data-stu-id="32eea-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="32eea-109">input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="32eea-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="32eea-110">Primo qubit di input.</span><span class="sxs-lookup"><span data-stu-id="32eea-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="32eea-111">INPUT1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="32eea-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="32eea-112">Secondo qubit di input.</span><span class="sxs-lookup"><span data-stu-id="32eea-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="32eea-113">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="32eea-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="32eea-114">Qubit su cui verrà applicata la funzione di maggioranza.</span><span class="sxs-lookup"><span data-stu-id="32eea-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="32eea-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32eea-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

