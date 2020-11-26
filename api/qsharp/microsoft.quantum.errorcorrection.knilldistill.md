---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operazione KnillDistill
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: df00c7572d909a67ec658bc8dccaf0e338afe5c5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200748"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="67640-102">Operazione KnillDistill</span><span class="sxs-lookup"><span data-stu-id="67640-102">KnillDistill operation</span></span>

<span data-ttu-id="67640-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="67640-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="67640-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67640-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67640-105">Implementa l'algoritmo di distillazione Magic state Knill.</span><span class="sxs-lookup"><span data-stu-id="67640-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="67640-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67640-106">Description</span></span>

<span data-ttu-id="67640-107">Date le 15 copie approssimative di uno stato magico $ $ \begin{align} \cos\frac{\Pi} {8} \ket {0} + \sin \frac{\Pi} {8} \ket {1} \end{align}, $ $ produce una copia di qualità superiore.</span><span class="sxs-lookup"><span data-stu-id="67640-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="67640-108">Input</span><span class="sxs-lookup"><span data-stu-id="67640-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="67640-109">roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="67640-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="67640-110">Un registro di quindici qubits contenenti copie approssimative di uno stato magico.</span><span class="sxs-lookup"><span data-stu-id="67640-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="67640-111">L'applicazione seguente di questa procedura di distillazione conterrà `roughMagic[0]` una copia di qualità superiore e il resto del registro verrà reimpostato sullo stato $ \ket{00\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="67640-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="67640-112">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="67640-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="67640-113">Se `true` , la procedura è stata completata e la copia di qualità superiore deve essere accettata.</span><span class="sxs-lookup"><span data-stu-id="67640-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="67640-114">Se `false` , la procedura ha avuto esito negativo e lo stato del registro deve essere considerato non definito.</span><span class="sxs-lookup"><span data-stu-id="67640-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="67640-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="67640-115">Remarks</span></span>

<span data-ttu-id="67640-116">Si segue l'algoritmo di Knill.</span><span class="sxs-lookup"><span data-stu-id="67640-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="67640-117">Tuttavia, l'implementazione attuale è lungi dall'essere ottimale, perché usa un numero eccessivo di qubits.</span><span class="sxs-lookup"><span data-stu-id="67640-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="67640-118">Gli stati magici vengono inseriti in questa routine, nel qual caso sono disponibili protocolli migliori.</span><span class="sxs-lookup"><span data-stu-id="67640-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="67640-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="67640-119">References</span></span>

- [<span data-ttu-id="67640-120">Knill</span><span class="sxs-lookup"><span data-stu-id="67640-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)