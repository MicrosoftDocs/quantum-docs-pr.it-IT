---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: Funzione _DeltaParityCNOTbitstring
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226078"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="29da0-102">Funzione _DeltaParityCNOTbitstring</span><span class="sxs-lookup"><span data-stu-id="29da0-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="29da0-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="29da0-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="29da0-104">Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="29da0-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="29da0-105">Passaggio di elaborazione classico di `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="29da0-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="29da0-106">Viene calcolato un elenco di qubits di controllo per la valutazione della differenza di parità tra due PQRS... termini di lunghezza pari.</span><span class="sxs-lookup"><span data-stu-id="29da0-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="29da0-107">Input</span><span class="sxs-lookup"><span data-stu-id="29da0-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="29da0-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="29da0-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="29da0-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="29da0-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="29da0-110">Output: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="29da0-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="29da0-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="29da0-111">Remarks</span></span>

<span data-ttu-id="29da0-112">Si presuppone che la lunghezza dei termini sia pari.</span><span class="sxs-lookup"><span data-stu-id="29da0-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="29da0-113">Calcola l'elenco di controlli per la differenza di parità tra due termini.</span><span class="sxs-lookup"><span data-stu-id="29da0-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="29da0-114">Si presuppone che gli elenchi di input siano ordinati in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="29da0-114">This assumes that the input lists is sorted in ascending order.</span></span>