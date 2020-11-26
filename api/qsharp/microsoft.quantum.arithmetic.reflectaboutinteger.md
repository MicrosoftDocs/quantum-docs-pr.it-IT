---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operazione ReflectAboutInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: d4bae0cba5ee45e8d48070e36efab0159ade9137
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222372"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="8b2ad-102">Operazione ReflectAboutInteger</span><span class="sxs-lookup"><span data-stu-id="8b2ad-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="8b2ad-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8b2ad-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8b2ad-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b2ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b2ad-105">Riflette un registro Quantum su un valore integer classico specificato.</span><span class="sxs-lookup"><span data-stu-id="8b2ad-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8b2ad-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b2ad-106">Description</span></span>

<span data-ttu-id="8b2ad-107">Dato un registro Quantum inizialmente nello stato $ \ sum_i \ alpha_i \ket{i} $, dove ogni $ \ket{i} $ è uno stato di base che rappresenta un numero intero $i $, riflette lo stato del registro sullo stato di base per un dato Integer $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="8b2ad-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="8b2ad-108">Input</span><span class="sxs-lookup"><span data-stu-id="8b2ad-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="8b2ad-109">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b2ad-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b2ad-110">Integer classico che indicizza lo stato di base su cui riflettere.</span><span class="sxs-lookup"><span data-stu-id="8b2ad-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="8b2ad-111">reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8b2ad-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="8b2ad-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b2ad-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8b2ad-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="8b2ad-113">Remarks</span></span>

<span data-ttu-id="8b2ad-114">Questa operazione viene implementata sul posto, senza allocazione esplicita di altri qubits ausiliari.</span><span class="sxs-lookup"><span data-stu-id="8b2ad-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>