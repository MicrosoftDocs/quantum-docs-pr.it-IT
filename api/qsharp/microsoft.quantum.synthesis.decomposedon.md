---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855521"
---
# <a name="decomposedon-function"></a><span data-ttu-id="777ab-102">DecomposedOn (funzione)</span><span class="sxs-lookup"><span data-stu-id="777ab-102">DecomposedOn function</span></span>

<span data-ttu-id="777ab-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="777ab-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="777ab-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="777ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="777ab-105">Scompone una permutazione su una variabile</span><span class="sxs-lookup"><span data-stu-id="777ab-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="777ab-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="777ab-106">Description</span></span>

<span data-ttu-id="777ab-107">Data una permutazione $ \Pi $ ( `perm` ) e un indice $i $ ( `index` ), questo metodo restituisce tre permutazioni $ ((\ pi_l, \ pi_r), \Pi ') $ in modo tale che le immagini di $ \ pi_l $ e $ \ pi_r $ non modifichino i bit nei rispettivi elementi a indici diversi da $i $ e immagini di $ \Pi ' $ non cambiano bit $i $ nei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="777ab-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="777ab-108">Input</span><span class="sxs-lookup"><span data-stu-id="777ab-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="777ab-109">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="777ab-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="777ab-110">Indice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="777ab-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="777ab-111">Output: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="777ab-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="777ab-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="777ab-112">Example</span></span>

<span data-ttu-id="777ab-113">Si supponga che l'input sia Perm = [0, 2, 3, 5, 7, 1, 4, 6] e index = 0, quindi questa funzione calcola tre permutazioni in base alla tabella seguente, che elenca la permutazione `perm` nella notazione binaria con gli elementi del gruppo a e le immagini nel gruppo D.  Le colonne elencano gli indici di bit.</span><span class="sxs-lookup"><span data-stu-id="777ab-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="777ab-114">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="777ab-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="777ab-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-115">2 1 0</span></span> | <span data-ttu-id="777ab-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-116">2 1 0</span></span> | <span data-ttu-id="777ab-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-117">2 1 0</span></span> | <span data-ttu-id="777ab-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="777ab-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-119">0 0 0</span></span> |       |       | <span data-ttu-id="777ab-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-120">0 0 0</span></span> | <span data-ttu-id="777ab-121">0</span><span class="sxs-lookup"><span data-stu-id="777ab-121">0</span></span>
| <span data-ttu-id="777ab-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-122">0 0 1</span></span> |       |       | <span data-ttu-id="777ab-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-123">0 1 0</span></span> | <span data-ttu-id="777ab-124">2</span><span class="sxs-lookup"><span data-stu-id="777ab-124">2</span></span>
| <span data-ttu-id="777ab-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-125">0 1 0</span></span> |       |       | <span data-ttu-id="777ab-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-126">0 1 1</span></span> | <span data-ttu-id="777ab-127">3</span><span class="sxs-lookup"><span data-stu-id="777ab-127">3</span></span>
| <span data-ttu-id="777ab-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-128">0 1 1</span></span> |       |       | <span data-ttu-id="777ab-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-129">1 0 1</span></span> | <span data-ttu-id="777ab-130">5</span><span class="sxs-lookup"><span data-stu-id="777ab-130">5</span></span>
| <span data-ttu-id="777ab-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-131">1 0 0</span></span> |       |       | <span data-ttu-id="777ab-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-132">1 1 1</span></span> | <span data-ttu-id="777ab-133">7</span><span class="sxs-lookup"><span data-stu-id="777ab-133">7</span></span>
| <span data-ttu-id="777ab-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-134">1 0 1</span></span> |       |       | <span data-ttu-id="777ab-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-135">0 0 1</span></span> | <span data-ttu-id="777ab-136">1</span><span class="sxs-lookup"><span data-stu-id="777ab-136">1</span></span>
| <span data-ttu-id="777ab-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-137">1 1 0</span></span> |       |       | <span data-ttu-id="777ab-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-138">1 0 0</span></span> | <span data-ttu-id="777ab-139">4</span><span class="sxs-lookup"><span data-stu-id="777ab-139">4</span></span>
| <span data-ttu-id="777ab-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-140">1 1 1</span></span> |       |       | <span data-ttu-id="777ab-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-141">1 1 0</span></span> | <span data-ttu-id="777ab-142">6</span><span class="sxs-lookup"><span data-stu-id="777ab-142">6</span></span>

<span data-ttu-id="777ab-143">Tutti i valori per gli indici non uguali a 0 (= index) vengono copiati da a a B e da D a C.</span><span class="sxs-lookup"><span data-stu-id="777ab-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="777ab-144">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="777ab-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="777ab-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-145">2 1 0</span></span> | <span data-ttu-id="777ab-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-146">2 1 0</span></span> | <span data-ttu-id="777ab-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-147">2 1 0</span></span> | <span data-ttu-id="777ab-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="777ab-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-149">0 0 0</span></span> | <span data-ttu-id="777ab-150">0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-150">0 0</span></span>   | <span data-ttu-id="777ab-151">0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-151">0 0</span></span>   | <span data-ttu-id="777ab-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-152">0 0 0</span></span> |
| <span data-ttu-id="777ab-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-153">0 0 1</span></span> | <span data-ttu-id="777ab-154">0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-154">0 0</span></span>   | <span data-ttu-id="777ab-155">0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-155">0 1</span></span>   | <span data-ttu-id="777ab-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-156">0 1 0</span></span> |
| <span data-ttu-id="777ab-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-157">0 1 0</span></span> | <span data-ttu-id="777ab-158">0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-158">0 1</span></span>   | <span data-ttu-id="777ab-159">0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-159">0 1</span></span>   | <span data-ttu-id="777ab-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-160">0 1 1</span></span> |
| <span data-ttu-id="777ab-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-161">0 1 1</span></span> | <span data-ttu-id="777ab-162">0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-162">0 1</span></span>   | <span data-ttu-id="777ab-163">1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-163">1 0</span></span>   | <span data-ttu-id="777ab-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-164">1 0 1</span></span> |
| <span data-ttu-id="777ab-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-165">1 0 0</span></span> | <span data-ttu-id="777ab-166">1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-166">1 0</span></span>   | <span data-ttu-id="777ab-167">1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-167">1 1</span></span>   | <span data-ttu-id="777ab-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-168">1 1 1</span></span> |
| <span data-ttu-id="777ab-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-169">1 0 1</span></span> | <span data-ttu-id="777ab-170">1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-170">1 0</span></span>   | <span data-ttu-id="777ab-171">0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-171">0 0</span></span>   | <span data-ttu-id="777ab-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-172">0 0 1</span></span> |
| <span data-ttu-id="777ab-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-173">1 1 0</span></span> | <span data-ttu-id="777ab-174">1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-174">1 1</span></span>   | <span data-ttu-id="777ab-175">1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-175">1 0</span></span>   | <span data-ttu-id="777ab-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-176">1 0 0</span></span> |
| <span data-ttu-id="777ab-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-177">1 1 1</span></span> | <span data-ttu-id="777ab-178">1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-178">1 1</span></span>   | <span data-ttu-id="777ab-179">1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-179">1 1</span></span>   | <span data-ttu-id="777ab-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-180">1 1 0</span></span> |

<span data-ttu-id="777ab-181">Viene quindi inserito un valore 0 per il primo elemento con un indice vuoto nella colonna 0 del blocco B, quindi un valore 1 viene inserito in B dove il prefisso corrisponde a (nel primo caso l'altra riga con indici 0 0).</span><span class="sxs-lookup"><span data-stu-id="777ab-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="777ab-182">Successivamente, un valore 1 viene aggiunto nella stessa riga del blocco C e quindi 0 per il prefisso corrispondente nel blocco C.  Questo processo viene ripetuto fino a quando tutti gli indici non sono stati inseriti nella colonna 0 nei blocchi B e C.</span><span class="sxs-lookup"><span data-stu-id="777ab-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="777ab-183">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="777ab-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="777ab-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-184">2 1 0</span></span> | <span data-ttu-id="777ab-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-185">2 1 0</span></span> | <span data-ttu-id="777ab-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-186">2 1 0</span></span> | <span data-ttu-id="777ab-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="777ab-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-188">0 0 0</span></span> | <span data-ttu-id="777ab-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-189">0 0 0</span></span> | <span data-ttu-id="777ab-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-190">0 0 0</span></span> | <span data-ttu-id="777ab-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-191">0 0 0</span></span> |
| <span data-ttu-id="777ab-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-192">0 0 1</span></span> | <span data-ttu-id="777ab-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-193">0 0 1</span></span> | <span data-ttu-id="777ab-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-194">0 1 1</span></span> | <span data-ttu-id="777ab-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-195">0 1 0</span></span> |
| <span data-ttu-id="777ab-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-196">0 1 0</span></span> | <span data-ttu-id="777ab-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-197">0 1 0</span></span> | <span data-ttu-id="777ab-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-198">0 1 0</span></span> | <span data-ttu-id="777ab-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-199">0 1 1</span></span> |
| <span data-ttu-id="777ab-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-200">0 1 1</span></span> | <span data-ttu-id="777ab-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-201">0 1 1</span></span> | <span data-ttu-id="777ab-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-202">1 0 1</span></span> | <span data-ttu-id="777ab-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-203">1 0 1</span></span> |
| <span data-ttu-id="777ab-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-204">1 0 0</span></span> | <span data-ttu-id="777ab-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-205">1 0 0</span></span> | <span data-ttu-id="777ab-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-206">1 1 0</span></span> | <span data-ttu-id="777ab-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-207">1 1 1</span></span> |
| <span data-ttu-id="777ab-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-208">1 0 1</span></span> | <span data-ttu-id="777ab-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-209">1 0 1</span></span> | <span data-ttu-id="777ab-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-210">0 0 1</span></span> | <span data-ttu-id="777ab-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="777ab-211">0 0 1</span></span> |
| <span data-ttu-id="777ab-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-212">1 1 0</span></span> | <span data-ttu-id="777ab-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-213">1 1 0</span></span> | <span data-ttu-id="777ab-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-214">1 0 0</span></span> | <span data-ttu-id="777ab-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="777ab-215">1 0 0</span></span> |
| <span data-ttu-id="777ab-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-216">1 1 1</span></span> | <span data-ttu-id="777ab-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-217">1 1 1</span></span> | <span data-ttu-id="777ab-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="777ab-218">1 1 1</span></span> | <span data-ttu-id="777ab-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="777ab-219">1 1 0</span></span> |

<span data-ttu-id="777ab-220">È possibile leggere tre nuove permutazioni dalla tabella:</span><span class="sxs-lookup"><span data-stu-id="777ab-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="777ab-221">$ \ pi_l $ con elementi in un oggetto, immagini in B (a sinistra)</span><span class="sxs-lookup"><span data-stu-id="777ab-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="777ab-222">$ \ pi_r $ con elementi in D, immagini in C (a destra)</span><span class="sxs-lookup"><span data-stu-id="777ab-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="777ab-223">$ \Pi ' $ con elementi in B, immagini in C (resto)</span><span class="sxs-lookup"><span data-stu-id="777ab-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="777ab-224">Si noti che i valori di bit di progettazione non cambiano in $ \ pi_l $ e $ \ pi_r $ per gli indici 1 e 2 e i valori di bit non cambiano per in $ \ pi_' $ per index 0.</span><span class="sxs-lookup"><span data-stu-id="777ab-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="777ab-225">Si noti inoltre che $ \ pi_l $ e $ \ pi_r $ devono essere autonomi.</span><span class="sxs-lookup"><span data-stu-id="777ab-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="777ab-226">Le permutazioni derivate e restituite sono: Left = [0, 1, 2, 3, 4, 5, 6, 7] right = [0, 1, 3, 2, 4, 5, 7, 6] resto = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="777ab-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>