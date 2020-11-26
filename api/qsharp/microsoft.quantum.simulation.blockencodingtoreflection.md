---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225347"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="6f4fa-102">BlockEncodingToReflection (funzione)</span><span class="sxs-lookup"><span data-stu-id="6f4fa-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="6f4fa-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6f4fa-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6f4fa-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f4fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f4fa-105">Converte un oggetto `BlockEncoding` in un oggetto equivalente `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="6f4fa-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="6f4fa-106">In altri casi, dato un `BlockEncoding` unity $U $ che codifica un operatore $H $ di interesse, lo converte in un `BlockEncodingReflection` $U ' $ che codifica lo stesso operatore, ma soddisfa anche $U ' ^ \Dagger = U ' $.</span><span class="sxs-lookup"><span data-stu-id="6f4fa-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="6f4fa-107">Questo aumenta le dimensioni del registro ausiliario di $U $ di un qubit.</span><span class="sxs-lookup"><span data-stu-id="6f4fa-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="6f4fa-108">Input</span><span class="sxs-lookup"><span data-stu-id="6f4fa-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="6f4fa-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="6f4fa-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="6f4fa-110">`BlockEncoding`Unitario $U $ da convertire in una reflection.</span><span class="sxs-lookup"><span data-stu-id="6f4fa-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="6f4fa-111">Output: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="6f4fa-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="6f4fa-112">Un $U unitario ' $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e soddisfa $U ' ^ \Dagger = U ' $.</span><span class="sxs-lookup"><span data-stu-id="6f4fa-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="6f4fa-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="6f4fa-113">Remarks</span></span>

<span data-ttu-id="6f4fa-114">Questo aumenta le dimensioni del registro ausiliario di $U $ di un qubit.</span><span class="sxs-lookup"><span data-stu-id="6f4fa-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="6f4fa-115">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="6f4fa-115">References</span></span>

- <span data-ttu-id="6f4fa-116">Simulazione Hamiltoniana di Qubitization Guang Hao low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="6f4fa-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="6f4fa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f4fa-117">See Also</span></span>

- [<span data-ttu-id="6f4fa-118">Microsoft. Quantum. Simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="6f4fa-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="6f4fa-119">Microsoft. Quantum. Simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="6f4fa-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)