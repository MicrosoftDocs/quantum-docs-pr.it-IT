---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: Funzione _ComputeJordanWignerBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714703"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="eed6c-102">Funzione _ComputeJordanWignerBitString</span><span class="sxs-lookup"><span data-stu-id="eed6c-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="eed6c-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="eed6c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="eed6c-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eed6c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eed6c-105">Calcola il componente Z della stringa Giordania-Wigner tra gli indici fermione in un operatore fermioniche con un numero pari di operatori di creazione/annientamento.</span><span class="sxs-lookup"><span data-stu-id="eed6c-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="eed6c-106">Input</span><span class="sxs-lookup"><span data-stu-id="eed6c-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="eed6c-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eed6c-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eed6c-108">Numero di fermioni nel sistema.</span><span class="sxs-lookup"><span data-stu-id="eed6c-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="eed6c-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="eed6c-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="eed6c-110">indici dell'operatore fermioniche.</span><span class="sxs-lookup"><span data-stu-id="eed6c-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="eed6c-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="eed6c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="eed6c-112">Bitstring in `Bool[]` `true` cui `PauliZ` deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="eed6c-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>