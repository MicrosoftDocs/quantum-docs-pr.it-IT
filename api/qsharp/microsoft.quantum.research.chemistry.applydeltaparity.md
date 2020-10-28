---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operazione ApplyDeltaParity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723978"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="4955d-102">Operazione ApplyDeltaParity</span><span class="sxs-lookup"><span data-stu-id="4955d-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="4955d-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4955d-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="4955d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4955d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4955d-105">Calcola la differenza di parità tra una PQRS precedente... termini e il PQRS successivo... termine.</span><span class="sxs-lookup"><span data-stu-id="4955d-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="4955d-106">Questa differenza viene calcolata in un qubit ausiliario.</span><span class="sxs-lookup"><span data-stu-id="4955d-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="4955d-107">Input</span><span class="sxs-lookup"><span data-stu-id="4955d-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="4955d-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4955d-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4955d-109">Elenco di indici per PQRS precedenti... termini.</span><span class="sxs-lookup"><span data-stu-id="4955d-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="4955d-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4955d-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4955d-111">Elenco di indici per PQRS successivi... termini.</span><span class="sxs-lookup"><span data-stu-id="4955d-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="4955d-112">Aux: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4955d-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4955d-113">Qubit ausiliari su cui vengono archiviati i risultati del calcolo della parità.</span><span class="sxs-lookup"><span data-stu-id="4955d-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="4955d-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4955d-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4955d-115">Qubit agito da tutti PQRS... termini.</span><span class="sxs-lookup"><span data-stu-id="4955d-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4955d-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4955d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4955d-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="4955d-117">Remarks</span></span>

<span data-ttu-id="4955d-118">Si presuppone che gli indici di P < Q < R < S <... sia per prevPQ che per nextPQ.</span><span class="sxs-lookup"><span data-stu-id="4955d-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>