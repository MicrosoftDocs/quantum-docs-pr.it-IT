---
title: 'Uso della libreria Microsoft Q # Numerics'
description: Informazioni sui tipi e le operazioni disponibili nella libreria Quantum Numerics di Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276115"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="cb7a9-103">Uso della libreria Numerics</span><span class="sxs-lookup"><span data-stu-id="cb7a9-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="cb7a9-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="cb7a9-104">Overview</span></span>

<span data-ttu-id="cb7a9-105">La libreria Numerics è costituita da tre componenti</span><span class="sxs-lookup"><span data-stu-id="cb7a9-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="cb7a9-106">**Aritmetica di base di interi** con comparatori e comparatori Integer</span><span class="sxs-lookup"><span data-stu-id="cb7a9-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="cb7a9-107">**Funzionalità Integer di alto livello** basata sulle funzionalità di base. include moltiplicazione, divisione, inversione e così via.  per gli interi con segno e senza segno.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="cb7a9-108">**Funzionalità aritmetica a virgola** fissa con inizializzazione a virgola fissa, addizione, moltiplicazione, reciproca, valutazione polinomiale e misurazione.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="cb7a9-109">È possibile accedere a tutti questi componenti utilizzando una singola `open` istruzione:</span><span class="sxs-lookup"><span data-stu-id="cb7a9-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="cb7a9-110">Tipi</span><span class="sxs-lookup"><span data-stu-id="cb7a9-110">Types</span></span>

<span data-ttu-id="cb7a9-111">La libreria Numerics supporta i tipi seguenti</span><span class="sxs-lookup"><span data-stu-id="cb7a9-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="cb7a9-112">**`LittleEndian`**: Matrice qubit `qArr : Qubit[]` che rappresenta un Integer in cui `qArr[0]` denota il bit meno significativo.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="cb7a9-113">**`SignedLittleEndian`**: Uguale a `LittleEndian` ad eccezione del fatto che rappresenta un intero con segno archiviato nel complemento a due.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="cb7a9-114">**`FixedPoint`**: Rappresenta un numero reale costituito da una matrice qubit `qArr2 : Qubit[]` e una posizione del punto binario `pos` , che conta il numero di cifre binarie a sinistra del punto binario.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="cb7a9-115">`qArr2`viene archiviato in modo analogo a `SignedLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="cb7a9-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="cb7a9-116">Gestione operativa</span><span class="sxs-lookup"><span data-stu-id="cb7a9-116">Operations</span></span>

<span data-ttu-id="cb7a9-117">Per ognuno dei tre tipi precedenti, è disponibile un'ampia gamma di operazioni:</span><span class="sxs-lookup"><span data-stu-id="cb7a9-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="cb7a9-118">Addizione</span><span class="sxs-lookup"><span data-stu-id="cb7a9-118">Addition</span></span>
    - <span data-ttu-id="cb7a9-119">Confronto</span><span class="sxs-lookup"><span data-stu-id="cb7a9-119">Comparison</span></span>
    - <span data-ttu-id="cb7a9-120">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="cb7a9-120">Multiplication</span></span>
    - <span data-ttu-id="cb7a9-121">Quadratura</span><span class="sxs-lookup"><span data-stu-id="cb7a9-121">Squaring</span></span>
    - <span data-ttu-id="cb7a9-122">Divisione (con resto)</span><span class="sxs-lookup"><span data-stu-id="cb7a9-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="cb7a9-123">Addizione</span><span class="sxs-lookup"><span data-stu-id="cb7a9-123">Addition</span></span>
    - <span data-ttu-id="cb7a9-124">Confronto</span><span class="sxs-lookup"><span data-stu-id="cb7a9-124">Comparison</span></span>
    - <span data-ttu-id="cb7a9-125">Complemento di Inversion modulo 2</span><span class="sxs-lookup"><span data-stu-id="cb7a9-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="cb7a9-126">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="cb7a9-126">Multiplication</span></span>
    - <span data-ttu-id="cb7a9-127">Quadratura</span><span class="sxs-lookup"><span data-stu-id="cb7a9-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="cb7a9-128">Preparazione/inizializzazione di valori classici</span><span class="sxs-lookup"><span data-stu-id="cb7a9-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="cb7a9-129">Addizione (costante classica o altro punto fisso Quantum)</span><span class="sxs-lookup"><span data-stu-id="cb7a9-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="cb7a9-130">Confronto</span><span class="sxs-lookup"><span data-stu-id="cb7a9-130">Comparison</span></span>
    - <span data-ttu-id="cb7a9-131">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="cb7a9-131">Multiplication</span></span>
    - <span data-ttu-id="cb7a9-132">Quadratura</span><span class="sxs-lookup"><span data-stu-id="cb7a9-132">Squaring</span></span>
    - <span data-ttu-id="cb7a9-133">Valutazione polinomiale con specializzazione per funzioni pari e dispari</span><span class="sxs-lookup"><span data-stu-id="cb7a9-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="cb7a9-134">Reciproco (1/x)</span><span class="sxs-lookup"><span data-stu-id="cb7a9-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="cb7a9-135">Misurazione (doppia classica)</span><span class="sxs-lookup"><span data-stu-id="cb7a9-135">Measurement (classical Double)</span></span>

<span data-ttu-id="cb7a9-136">Per ulteriori informazioni e documentazione dettagliata per ognuna di queste operazioni, vedere la documentazione di riferimento della libreria Q # in [docs.Microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="cb7a9-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="cb7a9-137">Esempio: aggiunta di numeri interi</span><span class="sxs-lookup"><span data-stu-id="cb7a9-137">Sample: Integer addition</span></span>

<span data-ttu-id="cb7a9-138">Come esempio di base, si consideri l'operazione $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $, ovvero un'operazione che accetta un integer n-qubit $x $ e un n-o (n + 1)-qubit registra $y $ come input, il secondo dei quali esegue il mapping alla somma $ (x + y) $.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="cb7a9-139">Si noti che la somma viene calcolata modulo $2 ^ n $ se $y $ viene archiviato in un registro $n $ bit.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="cb7a9-140">Utilizzando Quantum Development Kit, è possibile applicare questa operazione come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cb7a9-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="cb7a9-141">Esempio: valutazione di funzioni Smooth</span><span class="sxs-lookup"><span data-stu-id="cb7a9-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="cb7a9-142">Per valutare le funzioni smussate, ad esempio $ \sin (x) $ in un computer Quantum, dove $x $ è un `FixedPoint` numero quantico, la libreria Quantum Development Kit Numerics fornisce le operazioni `EvaluatePolynomialFxP` e `Evaluate[Even/Odd]PolynomialFxP` .</span><span class="sxs-lookup"><span data-stu-id="cb7a9-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="cb7a9-143">Il primo, `EvaluatePolynomialFxP` , consente di valutare un polinomio nel formato $ $ P (x) = A_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $ dove $d $ indica il *grado*.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="cb7a9-144">A tale scopo, sono necessari solo i coefficienti polinomiali `[a_0,..., a_d]` (di tipo `Double[]` ), l'input `x : FixedPoint` e l'output `y : FixedPoint` (inizialmente zero):</span><span class="sxs-lookup"><span data-stu-id="cb7a9-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="cb7a9-145">Il risultato, $P (x) = 1 + 2x $, verrà archiviato in `yFxP` .</span><span class="sxs-lookup"><span data-stu-id="cb7a9-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="cb7a9-146">Il secondo, `EvaluateEvenPolynomialFxP` , e il terzo, `EvaluateOddPolynomialFxP` , sono specializzazioni per i casi di funzioni even e Odd, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="cb7a9-147">Ovvero, per una funzione uniforme/dispari $f (x) $ e $ $ P_ {even} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ è approssimato bene $P _ {even} (x) $ o $P _ {Odd} (x): = x\cdot P_ {even} (x) $, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="cb7a9-148">In Q # questi due casi possono essere gestiti come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cb7a9-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="cb7a9-149">che valuta $P _ {even} (x) = 1 + 2x ^ 2 $ e</span><span class="sxs-lookup"><span data-stu-id="cb7a9-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="cb7a9-150">che valuta $P _ {Odd} (x) = x + 2x ^ 3 $.</span><span class="sxs-lookup"><span data-stu-id="cb7a9-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="cb7a9-151">Altri esempi</span><span class="sxs-lookup"><span data-stu-id="cb7a9-151">More samples</span></span>

<span data-ttu-id="cb7a9-152">Altri esempi sono disponibili nel [repository principale degli esempi](https://github.com/Microsoft/Quantum).</span><span class="sxs-lookup"><span data-stu-id="cb7a9-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="cb7a9-153">Per iniziare, clonare il repository e aprire la `Numerics` sottocartella:</span><span class="sxs-lookup"><span data-stu-id="cb7a9-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="cb7a9-154">Quindi, `cd` in una delle cartelle di esempio ed eseguire l'esempio tramite</span><span class="sxs-lookup"><span data-stu-id="cb7a9-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
