---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: Funzione _ComputeJordanWignerBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839536"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="c19df-102">Funzione _ComputeJordanWignerBitString</span><span class="sxs-lookup"><span data-stu-id="c19df-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="c19df-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="c19df-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="c19df-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c19df-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="c19df-105">Calcola il componente Z della stringa Giordania-Wigner tra gli indici fermione in un operatore fermioniche con un numero pari di operatori di creazione/annientamento.</span><span class="sxs-lookup"><span data-stu-id="c19df-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="c19df-106">Input</span><span class="sxs-lookup"><span data-stu-id="c19df-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="c19df-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c19df-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c19df-108">Numero di fermioni nel sistema.</span><span class="sxs-lookup"><span data-stu-id="c19df-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="c19df-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c19df-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c19df-110">indici dell'operatore fermioniche.</span><span class="sxs-lookup"><span data-stu-id="c19df-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c19df-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="c19df-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="c19df-112">Bitstring in `Bool[]` `true` cui `PauliZ` deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="c19df-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="c19df-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c19df-113">Example</span></span>

<span data-ttu-id="c19df-114">Let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]); bitString è [false, false, false, true, true, true, false].</span><span class="sxs-lookup"><span data-stu-id="c19df-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>