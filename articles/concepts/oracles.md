---
title: Oracoli quantistici
description: Informazioni su come usare e definire Oracle Quantum, black box operazioni usate come input per un altro algoritmo.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630311"
---
# <a name="quantum-oracles"></a><span data-ttu-id="76586-103">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="76586-103">Quantum Oracles</span></span>

<span data-ttu-id="76586-104">Un $O Oracle $ è un'operazione "black box" utilizzata come input per un altro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="76586-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="76586-105">Tali operazioni vengono spesso definite utilizzando una funzione classica $f: \\ {0, 1 \\ } ^ n per \\ {0, 1 \\ } ^ m $ , che accetta un $ input binario a $n bit e produce un output binario a $m $ bit.</span><span class="sxs-lookup"><span data-stu-id="76586-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="76586-106">A tale scopo, si consideri un particolare input binario $x = (x_ {0 } , x_ {1 } , \dots, x_ {n-1 } ) $.</span><span class="sxs-lookup"><span data-stu-id="76586-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="76586-107">È possibile etichettare gli Stati qubit come $ \ket { \vec{x } } = \ket{x_ {0 } } \otimes \ket{x_ {1} \otimes \cdots \otimes \ket{ } x_ {n-1 } } $.</span><span class="sxs-lookup"><span data-stu-id="76586-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="76586-108">È possibile prima di tutto tentare di definire $O in $ modo che $O \ket {x } = \ket{f (x)} $, ma ciò presenta un paio di problemi.</span><span class="sxs-lookup"><span data-stu-id="76586-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="76586-109">In primo luogo, $f $ possono avere dimensioni diverse di input e output ($n \ne m $ ), in modo che l'applicazione di $O $ modifichi il numero di qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="76586-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="76586-110">In secondo luogo, anche se $n = m $ , la funzione potrebbe non essere invertibile: se $f (x) = f (y) $ per alcuni $x \ne y $ , quindi $O \ket {x } = o \ket {y } $ ma $O ^ \dagger o \ket {x } \ne o ^ \dagger o \ket {y } $.</span><span class="sxs-lookup"><span data-stu-id="76586-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="76586-111">Ciò significa che non sarà possibile costruire l'operazione contigua $O ^ \dagger $ e che per tali Oracle deve essere definito un oggetto adiacente.</span><span class="sxs-lookup"><span data-stu-id="76586-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="76586-112">Definizione di un Oracle per effetto sugli stati di base di calcolo</span><span class="sxs-lookup"><span data-stu-id="76586-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="76586-113">È possibile gestire entrambi questi problemi introducendo un secondo registro di $m $ qubits per la risposta.</span><span class="sxs-lookup"><span data-stu-id="76586-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="76586-114">Si definirà quindi l'effetto di Oracle su tutti gli Stati di base computazionale: per tutti $x \In \\ {0, 1 \\ } ^ n $ e $y \In \\ {0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="76586-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="76586-115">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="76586-115">$$ \begin{align}</span></span>
    <span data-ttu-id="76586-116">O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="76586-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="76586-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="76586-117">\end{align}</span></span>
$$

<span data-ttu-id="76586-118">A questo punto $O = O ^ \dagger $ per costruzione, quindi sono stati risolti entrambi i problemi precedenti.</span><span class="sxs-lookup"><span data-stu-id="76586-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="76586-119">Per verificare che $O = O ^ {\dagger } $, si noti che $O ^ 2 = \boldone $ da $a \oplus b \oplus b = a $ per tutti $a, b \In \{ 0, 1 \} $.</span><span class="sxs-lookup"><span data-stu-id="76586-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="76586-120">Di conseguenza, $O \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y } $.</span><span class="sxs-lookup"><span data-stu-id="76586-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="76586-121">In particolare, la definizione di un Oracle in questo modo per ogni stato di base computazionale $ \ket{x } \ket{y } $ definisce anche il modo in cui $O $ agisce per qualsiasi altro stato.</span><span class="sxs-lookup"><span data-stu-id="76586-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="76586-122">Questa operazione segue immediatamente il fatto che $O $ , come tutte le operazioni Quantum, è lineare nello stato su cui agisce.</span><span class="sxs-lookup"><span data-stu-id="76586-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="76586-123">Si consideri l'operazione Hadamard, ad esempio, definita da $H \ket{0 } = \ket { +} $ e $H \ket{1 } = \ket { -} $.</span><span class="sxs-lookup"><span data-stu-id="76586-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="76586-124">Se si vuole ottenere informazioni su come $H $ agisce su $ \ket { +} $, è possibile usare tale $H $ lineare,</span><span class="sxs-lookup"><span data-stu-id="76586-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="76586-125">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="76586-125">$$ \begin{align}</span></span>
<span data-ttu-id="76586-126">H \ket { +} & = \frac{1 } {\sqrt{2 } } h (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (h \ket {0 } + h \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="76586-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="76586-127">\end{align}</span><span class="sxs-lookup"><span data-stu-id="76586-127">\end{align}</span></span>
$$

<span data-ttu-id="76586-128">Nel caso di definire il $O Oracle $ , è possibile usare in modo analogo che qualsiasi stato $ \ket { \psi } $ su $n + m $ qubits può essere scritto come</span><span class="sxs-lookup"><span data-stu-id="76586-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="76586-129">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="76586-129">$$ \begin{align}</span></span>
<span data-ttu-id="76586-130">\ket { \psi } & = \ Sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="76586-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="76586-131">\end{align}</span><span class="sxs-lookup"><span data-stu-id="76586-131">\end{align}</span></span>
$$

<span data-ttu-id="76586-132">dove $ \Alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ m per \mathbb{C } $ rappresenta i coefficienti dello stato $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="76586-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="76586-133">Pertanto</span><span class="sxs-lookup"><span data-stu-id="76586-133">Thus,</span></span>

<span data-ttu-id="76586-134">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="76586-134">$$ \begin{align}</span></span>
<span data-ttu-id="76586-135">O \ket { \psi } & = O \ Sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ Sum_ {x \In \\ {0,1} \\ ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ Sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0,1 \\ } ^ m } \Alpha (x, y) \ket{x \ket{y \oplus } f (x)}.</span><span class="sxs-lookup"><span data-stu-id="76586-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="76586-136">\end{align}</span><span class="sxs-lookup"><span data-stu-id="76586-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="76586-137">Oracle della fase</span><span class="sxs-lookup"><span data-stu-id="76586-137">Phase oracles</span></span>
<span data-ttu-id="76586-138">In alternativa, è possibile codificare $f $ in un $O Oracle $ applicando una _fase_ basata sull'input per $O $ .</span><span class="sxs-lookup"><span data-stu-id="76586-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="76586-139">È ad esempio possibile definire $O $ tale che $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="76586-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="76586-140">O \ket{x } = (-1) ^ {f (x)} \ket{x } .</span><span class="sxs-lookup"><span data-stu-id="76586-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="76586-141">\end{align}</span><span class="sxs-lookup"><span data-stu-id="76586-141">\end{align}</span></span>
<span data-ttu-id="76586-142">$ $ Se una fase Oracle agisce inizialmente su un registro con uno stato di base computazionale $ \ket{x } $, questa fase è una fase globale e pertanto non è osservabile.</span><span class="sxs-lookup"><span data-stu-id="76586-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="76586-143">Tale Oracle, tuttavia, può essere una risorsa molto potente se applicata a una superposizione o come operazione controllata.</span><span class="sxs-lookup"><span data-stu-id="76586-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="76586-144">Si consideri, ad esempio, una fase Orcale $O _f $ per una funzione single-qubit $f $ .</span><span class="sxs-lookup"><span data-stu-id="76586-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="76586-145">Quindi, $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="76586-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="76586-146">O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}.</span><span class="sxs-lookup"><span data-stu-id="76586-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="76586-147">\end{align}</span><span class="sxs-lookup"><span data-stu-id="76586-147">\end{align}</span></span>
$$

<span data-ttu-id="76586-148">Più in generale, entrambe le visualizzazioni di Oracle possono essere ampliate per rappresentare funzioni classiche che restituiscono numeri reali anziché solo un bit singolo.</span><span class="sxs-lookup"><span data-stu-id="76586-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="76586-149">La scelta del modo migliore per implementare un Oracle dipende in larga misura dal modo in cui tale Oracle verrà utilizzato all'interno di un determinato algoritmo.</span><span class="sxs-lookup"><span data-stu-id="76586-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="76586-150">Ad esempio, l' [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) si basa su Oracle implementato nel primo modo, mentre l' [algoritmo di Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) si basa su Oracle implementato nel secondo modo.</span><span class="sxs-lookup"><span data-stu-id="76586-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="76586-151">Per altri dettagli, è consigliabile discutere in [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="76586-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
