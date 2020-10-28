---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722071"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="5b7f9-102">BlockEncodingToReflection (funzione)</span><span class="sxs-lookup"><span data-stu-id="5b7f9-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="5b7f9-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5b7f9-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5b7f9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5b7f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5b7f9-105">Converte un oggetto `BlockEncoding` in un oggetto equivalente `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="5b7f9-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="5b7f9-106">In altri casi, dato un `BlockEncoding` unity $U $ che codifica un operatore $H $ di interesse, lo converte in un `BlockEncodingReflection` $U ' $ che codifica lo stesso operatore, ma soddisfa anche $U ' ^ \Dagger = U ' $.</span><span class="sxs-lookup"><span data-stu-id="5b7f9-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="5b7f9-107">Questo aumenta le dimensioni del registro ausiliario di $U $ di un qubit.</span><span class="sxs-lookup"><span data-stu-id="5b7f9-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="5b7f9-108">Input</span><span class="sxs-lookup"><span data-stu-id="5b7f9-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="5b7f9-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="5b7f9-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="5b7f9-110">`BlockEncoding`Unitario $U $ da convertire in una reflection.</span><span class="sxs-lookup"><span data-stu-id="5b7f9-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="5b7f9-111">Output: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="5b7f9-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="5b7f9-112">Un $U unitario ' $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e soddisfa $U ' ^ \Dagger = U ' $.</span><span class="sxs-lookup"><span data-stu-id="5b7f9-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="5b7f9-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="5b7f9-113">Remarks</span></span>

<span data-ttu-id="5b7f9-114">Questo aumenta le dimensioni del registro ausiliario di $U $ di un qubit.</span><span class="sxs-lookup"><span data-stu-id="5b7f9-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="5b7f9-115">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5b7f9-115">References</span></span>

- <span data-ttu-id="5b7f9-116">Simulazione Hamiltoniana di Qubitization Guang Hao low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="5b7f9-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="5b7f9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b7f9-117">See Also</span></span>

- [<span data-ttu-id="5b7f9-118">Microsoft. Quantum. Simulation. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="5b7f9-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="5b7f9-119">Microsoft. Quantum. Simulation. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="5b7f9-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)