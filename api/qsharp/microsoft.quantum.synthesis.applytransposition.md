---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operazione ApplyTransposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203315"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="83641-102">Operazione ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="83641-102">ApplyTransposition operation</span></span>

<span data-ttu-id="83641-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="83641-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="83641-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83641-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="83641-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83641-105">Description</span></span>

<span data-ttu-id="83641-106">Questa operazione scambia l'ampiezza in corrispondenza dell'indice `a` con l'ampiezza in corrispondenza dell'indice `b` nel vettore di stato specificato di `register` lunghezza $n $.</span><span class="sxs-lookup"><span data-stu-id="83641-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="83641-107">Se `a` è uguale `b` a, il vettore di stato non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="83641-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="83641-108">Input</span><span class="sxs-lookup"><span data-stu-id="83641-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="83641-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83641-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83641-110">Primo indice (deve essere un valore compreso tra 0 e $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="83641-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="83641-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83641-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83641-112">Secondo indice (deve essere un valore compreso tra 0 e $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="83641-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="83641-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="83641-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="83641-114">Elenco di $n $ qubits a cui viene applicata la trasposizione.</span><span class="sxs-lookup"><span data-stu-id="83641-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="83641-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83641-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

