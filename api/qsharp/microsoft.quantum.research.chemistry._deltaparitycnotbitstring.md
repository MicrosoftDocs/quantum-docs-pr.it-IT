---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: Funzione _DeltaParityCNOTbitstring
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847608"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="74c2e-102">Funzione _DeltaParityCNOTbitstring</span><span class="sxs-lookup"><span data-stu-id="74c2e-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="74c2e-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="74c2e-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="74c2e-104">Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="74c2e-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="74c2e-105">Passaggio di elaborazione classico di `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="74c2e-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="74c2e-106">Viene calcolato un elenco di qubits di controllo per la valutazione della differenza di parità tra due PQRS... termini di lunghezza pari.</span><span class="sxs-lookup"><span data-stu-id="74c2e-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="74c2e-107">Input</span><span class="sxs-lookup"><span data-stu-id="74c2e-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="74c2e-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="74c2e-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="74c2e-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="74c2e-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="74c2e-110">Output: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="74c2e-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="74c2e-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="74c2e-111">Remarks</span></span>

<span data-ttu-id="74c2e-112">Si presuppone che la lunghezza dei termini sia pari.</span><span class="sxs-lookup"><span data-stu-id="74c2e-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="74c2e-113">Calcola l'elenco di controlli per la differenza di parità tra due termini.</span><span class="sxs-lookup"><span data-stu-id="74c2e-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="74c2e-114">Si presuppone che gli elenchi di input siano ordinati in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="74c2e-114">This assumes that the input lists is sorted in ascending order.</span></span>