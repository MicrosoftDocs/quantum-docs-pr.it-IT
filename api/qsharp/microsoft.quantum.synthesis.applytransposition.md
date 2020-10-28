---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operazione ApplyTransposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725263"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="140d3-102">Operazione ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="140d3-102">ApplyTransposition operation</span></span>

<span data-ttu-id="140d3-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="140d3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="140d3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="140d3-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="140d3-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="140d3-105">Description</span></span>

<span data-ttu-id="140d3-106">Questa operazione scambia l'ampiezza in corrispondenza dell'indice `a` con l'ampiezza in corrispondenza dell'indice `b` nel vettore di stato specificato di `register` lunghezza $n $.</span><span class="sxs-lookup"><span data-stu-id="140d3-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="140d3-107">Se `a` è uguale `b` a, il vettore di stato non viene modificato.</span><span class="sxs-lookup"><span data-stu-id="140d3-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="140d3-108">Input</span><span class="sxs-lookup"><span data-stu-id="140d3-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="140d3-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="140d3-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="140d3-110">Primo indice (deve essere un valore compreso tra 0 e $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="140d3-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="140d3-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="140d3-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="140d3-112">Secondo indice (deve essere un valore compreso tra 0 e $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="140d3-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="140d3-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="140d3-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="140d3-114">Elenco di $n $ qubits a cui viene applicata la trasposizione.</span><span class="sxs-lookup"><span data-stu-id="140d3-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="140d3-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="140d3-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

