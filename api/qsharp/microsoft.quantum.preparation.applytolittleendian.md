---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Operazione ApplyToLittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: 1194ac369d2d474330357d26dd22709e9c68dd6e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226486"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="3f712-102">Operazione ApplyToLittleEndian</span><span class="sxs-lookup"><span data-stu-id="3f712-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="3f712-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3f712-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3f712-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f712-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f712-105">Applica un'operazione ai qubits sottostanti che costituiscono un registro little-endian.</span><span class="sxs-lookup"><span data-stu-id="3f712-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="3f712-106">Questa operazione è contrassegnata come interna, perché un registro Little-Endian è pensato come "opaco", in modo che questo sia solo un dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="3f712-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3f712-107">Input</span><span class="sxs-lookup"><span data-stu-id="3f712-107">Input</span></span>

### <a name="bareop--qubit--unit--is-adj--ctl"></a><span data-ttu-id="3f712-108">bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="3f712-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="3f712-109">registra: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f712-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="3f712-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f712-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

