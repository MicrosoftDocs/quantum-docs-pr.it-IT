---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: Funzione _DeltaParityCNOTbitstring
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710853"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="73c8a-102">Funzione _DeltaParityCNOTbitstring</span><span class="sxs-lookup"><span data-stu-id="73c8a-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="73c8a-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="73c8a-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="73c8a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="73c8a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="73c8a-105">Passaggio di elaborazione classico di `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="73c8a-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="73c8a-106">Viene calcolato un elenco di qubits di controllo per la valutazione della differenza di parità tra due PQRS... termini di lunghezza pari.</span><span class="sxs-lookup"><span data-stu-id="73c8a-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="73c8a-107">Input</span><span class="sxs-lookup"><span data-stu-id="73c8a-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="73c8a-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="73c8a-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="73c8a-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="73c8a-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="73c8a-110">Output: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="73c8a-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="73c8a-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="73c8a-111">Remarks</span></span>

<span data-ttu-id="73c8a-112">Si presuppone che la lunghezza dei termini sia pari.</span><span class="sxs-lookup"><span data-stu-id="73c8a-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="73c8a-113">Calcola l'elenco di controlli per la differenza di parità tra due termini.</span><span class="sxs-lookup"><span data-stu-id="73c8a-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="73c8a-114">Si presuppone che gli elenchi di input siano ordinati in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="73c8a-114">This assumes that the input lists is sorted in ascending order.</span></span>