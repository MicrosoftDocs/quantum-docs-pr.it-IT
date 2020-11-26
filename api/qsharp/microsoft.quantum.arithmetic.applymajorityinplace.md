---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Operazione ApplyMajorityInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190735"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="84844-102">Operazione ApplyMajorityInPlace</span><span class="sxs-lookup"><span data-stu-id="84844-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="84844-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="84844-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="84844-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84844-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84844-105">Applica l'operazione di maggioranza dei tre qubit sul posto in un registro di qubits.</span><span class="sxs-lookup"><span data-stu-id="84844-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="84844-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84844-106">Description</span></span>

<span data-ttu-id="84844-107">Questa operazione calcola la funzione di maggioranza sul posto su 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="84844-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="84844-108">Se si denota output qubit come $z $ e input qubits come $x $ e $y $, l'operazione esegue la trasformazione seguente: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="84844-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="84844-109">Input</span><span class="sxs-lookup"><span data-stu-id="84844-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="84844-110">output: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="84844-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="84844-111">Primo input qubit.</span><span class="sxs-lookup"><span data-stu-id="84844-111">First input qubit.</span></span> <span data-ttu-id="84844-112">Si noti che l'output viene calcolato sul posto e archiviato in questo qubit.</span><span class="sxs-lookup"><span data-stu-id="84844-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="84844-113">input: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="84844-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="84844-114">Secondo e terzo qubits di input.</span><span class="sxs-lookup"><span data-stu-id="84844-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="84844-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84844-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

