---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operazione ReflectAboutInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719715"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="f806b-102">Operazione ReflectAboutInteger</span><span class="sxs-lookup"><span data-stu-id="f806b-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="f806b-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f806b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f806b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f806b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f806b-105">Riflette un registro Quantum su un valore integer classico specificato.</span><span class="sxs-lookup"><span data-stu-id="f806b-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f806b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f806b-106">Description</span></span>

<span data-ttu-id="f806b-107">Dato un registro Quantum inizialmente nello stato $ \ sum_i \ alpha_i \ket{i} $, dove ogni $ \ket{i} $ è uno stato di base che rappresenta un numero intero $i $, riflette lo stato del registro sullo stato di base per un dato Integer $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $</span><span class="sxs-lookup"><span data-stu-id="f806b-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="f806b-108">Input</span><span class="sxs-lookup"><span data-stu-id="f806b-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="f806b-109">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f806b-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f806b-110">Integer classico che indicizza lo stato di base su cui riflettere.</span><span class="sxs-lookup"><span data-stu-id="f806b-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="f806b-111">reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f806b-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="f806b-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f806b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f806b-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="f806b-113">Remarks</span></span>

<span data-ttu-id="f806b-114">Questa operazione viene implementata sul posto, senza allocazione esplicita di altri qubits ausiliari.</span><span class="sxs-lookup"><span data-stu-id="f806b-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>