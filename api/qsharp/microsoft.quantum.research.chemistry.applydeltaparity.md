---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operazione ApplyDeltaParity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851103"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="c0efc-102">Operazione ApplyDeltaParity</span><span class="sxs-lookup"><span data-stu-id="c0efc-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="c0efc-103">Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c0efc-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c0efc-104">Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c0efc-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="c0efc-105">Calcola la differenza di parità tra una PQRS precedente... termini e il PQRS successivo... termine.</span><span class="sxs-lookup"><span data-stu-id="c0efc-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="c0efc-106">Questa differenza viene calcolata in un qubit ausiliario.</span><span class="sxs-lookup"><span data-stu-id="c0efc-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c0efc-107">Input</span><span class="sxs-lookup"><span data-stu-id="c0efc-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="c0efc-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c0efc-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c0efc-109">Elenco di indici per PQRS precedenti... termini.</span><span class="sxs-lookup"><span data-stu-id="c0efc-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="c0efc-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c0efc-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c0efc-111">Elenco di indici per PQRS successivi... termini.</span><span class="sxs-lookup"><span data-stu-id="c0efc-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="c0efc-112">Aux: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c0efc-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c0efc-113">Qubit ausiliari su cui vengono archiviati i risultati del calcolo della parità.</span><span class="sxs-lookup"><span data-stu-id="c0efc-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c0efc-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c0efc-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c0efc-115">Qubit agito da tutti PQRS... termini.</span><span class="sxs-lookup"><span data-stu-id="c0efc-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0efc-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0efc-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c0efc-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="c0efc-117">Remarks</span></span>

<span data-ttu-id="c0efc-118">Si presuppone che gli indici di P < Q < R < S <... sia per prevPQ che per nextPQ.</span><span class="sxs-lookup"><span data-stu-id="c0efc-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>