---
<span data-ttu-id="aa1b8-101">title: Quantum Oracles Description: informazioni su come usare e definire Oracle Quantum, black box operazioni usate come input per un altro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="aa1b8-102">autore: cgranade UID: Microsoft. Quantum. Concepts. Oracles ms. Author: chgranad ms. Date: 07/11/2018 ms. Topic: Conceptual no-loc:</span><span class="sxs-lookup"><span data-stu-id="aa1b8-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: chgranad ms.date: 07/11/2018 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="aa1b8-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-103">"Q#"</span></span>
- <span data-ttu-id="aa1b8-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-104">"$$v"</span></span>
- <span data-ttu-id="aa1b8-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-105">"$$"</span></span>
- <span data-ttu-id="aa1b8-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-106">"$$"</span></span>
- <span data-ttu-id="aa1b8-107">"$"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-107">"$"</span></span>
- <span data-ttu-id="aa1b8-108">"$"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-108">"$"</span></span>
- <span data-ttu-id="aa1b8-109">"$"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-109">"$"</span></span>
- <span data-ttu-id="aa1b8-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-110">"$$"</span></span>
- <span data-ttu-id="aa1b8-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-111">"\cdots"</span></span>
- <span data-ttu-id="aa1b8-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-112">"bmatrix"</span></span>
- <span data-ttu-id="aa1b8-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-113">"\ddots"</span></span>
- <span data-ttu-id="aa1b8-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-114">"\equiv"</span></span>
- <span data-ttu-id="aa1b8-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-115">"\sum"</span></span>
- <span data-ttu-id="aa1b8-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-116">"\begin"</span></span>
- <span data-ttu-id="aa1b8-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-117">"\end"</span></span>
- <span data-ttu-id="aa1b8-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-118">"\sqrt"</span></span>
- <span data-ttu-id="aa1b8-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-119">"\otimes"</span></span>
- <span data-ttu-id="aa1b8-120">"{"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-120">"{"</span></span>
- <span data-ttu-id="aa1b8-121">"}"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-121">"}"</span></span>
- <span data-ttu-id="aa1b8-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-122">"\text"</span></span>
- <span data-ttu-id="aa1b8-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-123">"\phi"</span></span>
- <span data-ttu-id="aa1b8-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-124">"\kappa"</span></span>
- <span data-ttu-id="aa1b8-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-125">"\psi"</span></span>
- <span data-ttu-id="aa1b8-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-126">"\alpha"</span></span>
- <span data-ttu-id="aa1b8-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-127">"\beta"</span></span>
- <span data-ttu-id="aa1b8-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-128">"\gamma"</span></span>
- <span data-ttu-id="aa1b8-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-129">"\delta"</span></span>
- <span data-ttu-id="aa1b8-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-130">"\omega"</span></span>
- <span data-ttu-id="aa1b8-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-131">"\bra"</span></span>
- <span data-ttu-id="aa1b8-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-132">"\ket"</span></span>
- <span data-ttu-id="aa1b8-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-133">"\boldone"</span></span>
- <span data-ttu-id="aa1b8-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-134">"\\\\"</span></span>
- <span data-ttu-id="aa1b8-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-135">"\\"</span></span>
- <span data-ttu-id="aa1b8-136">"="</span><span class="sxs-lookup"><span data-stu-id="aa1b8-136">"="</span></span>
- <span data-ttu-id="aa1b8-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-137">"\frac"</span></span>
- <span data-ttu-id="aa1b8-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-138">"\text"</span></span>
- <span data-ttu-id="aa1b8-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-139">"\mapsto"</span></span>
- <span data-ttu-id="aa1b8-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-140">"\dagger"</span></span>
- <span data-ttu-id="aa1b8-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-141">"\to"</span></span>
- <span data-ttu-id="aa1b8-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-142">"\begin{cases}"</span></span>
- <span data-ttu-id="aa1b8-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-143">"\end{cases}"</span></span>
- <span data-ttu-id="aa1b8-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-144">"\operatorname"</span></span>
- <span data-ttu-id="aa1b8-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-145">"\braket"</span></span>
- <span data-ttu-id="aa1b8-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-146">"\id"</span></span>
- <span data-ttu-id="aa1b8-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-147">"\expect"</span></span>
- <span data-ttu-id="aa1b8-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-148">"\defeq"</span></span>
- <span data-ttu-id="aa1b8-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-149">"\variance"</span></span>
- <span data-ttu-id="aa1b8-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-150">"\dd"</span></span>
- <span data-ttu-id="aa1b8-151">"&"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-151">"&"</span></span>
- <span data-ttu-id="aa1b8-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-152">"\begin{align}"</span></span>
- <span data-ttu-id="aa1b8-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-153">"\end{align}"</span></span>
- <span data-ttu-id="aa1b8-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-154">"\Lambda"</span></span>
- <span data-ttu-id="aa1b8-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-155">"\lambda"</span></span>
- <span data-ttu-id="aa1b8-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-156">"\Omega"</span></span>
- <span data-ttu-id="aa1b8-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-157">"\mathrm"</span></span>
- <span data-ttu-id="aa1b8-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-158">"\left"</span></span>
- <span data-ttu-id="aa1b8-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-159">"\right"</span></span>
- <span data-ttu-id="aa1b8-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-160">"\qquad"</span></span>
- <span data-ttu-id="aa1b8-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-161">"\times"</span></span>
- <span data-ttu-id="aa1b8-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-162">"\big"</span></span>
- <span data-ttu-id="aa1b8-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-163">"\langle"</span></span>
- <span data-ttu-id="aa1b8-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-164">"\rangle"</span></span>
- <span data-ttu-id="aa1b8-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-165">"\bigg"</span></span>
- <span data-ttu-id="aa1b8-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-166">"\Big"</span></span>
- <span data-ttu-id="aa1b8-167">"|"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-167">"|"</span></span>
- <span data-ttu-id="aa1b8-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-168">"\mathbb"</span></span>
- <span data-ttu-id="aa1b8-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-169">"\vec"</span></span>
- <span data-ttu-id="aa1b8-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-170">"\in"</span></span>
- <span data-ttu-id="aa1b8-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-171">"\texttt"</span></span>
- <span data-ttu-id="aa1b8-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-172">"\ne"</span></span>
- <span data-ttu-id="aa1b8-173">"<"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-173">"<"</span></span>
- <span data-ttu-id="aa1b8-174">">"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-174">">"</span></span>
- <span data-ttu-id="aa1b8-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-175">"\leq"</span></span>
- <span data-ttu-id="aa1b8-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-176">"\geq"</span></span>
- <span data-ttu-id="aa1b8-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-177">"~~"</span></span>
- <span data-ttu-id="aa1b8-178">"~"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-178">"~"</span></span>
- <span data-ttu-id="aa1b8-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="aa1b8-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="aa1b8-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="aa1b8-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="aa1b8-182">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="aa1b8-182">Quantum Oracles</span></span>

<span data-ttu-id="aa1b8-183">Un $ O Oracle $ è un'operazione "black box" utilizzata come input per un altro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="aa1b8-184">Spesso, tali operazioni vengono definite utilizzando una funzione classica $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ che accetta un $ $ input binario a n bit e produce un $ $ output binario a m bit.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="aa1b8-185">A tale scopo, si consideri un particolare input binario $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="aa1b8-186">È possibile etichettare gli Stati qubit come $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="aa1b8-187">Si può prima di tutto tentare di definire $ o in $ modo che $ o \ket { x } = \ket { f (x) } $ , ma si siano verificati alcuni problemi.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="aa1b8-188">Per prima cosa, $ f $ potrebbe avere dimensioni diverse di input e output ( $ n \ne m $ ), in modo che l'applicazione di $ O $ modifichi il numero di qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="aa1b8-189">In secondo luogo, anche se $ n = m $ , la funzione non può essere invertibile: se $ f (x) = f (y) $ per alcuni $ x \ne y $ , $ o \ket { x } = o \ket { y } $ ma $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="aa1b8-190">Ciò significa che non sarà possibile costruire l'operazione contigua $ O ^ \dagger $ e per i Oracle è necessario che sia definito un oggetto adiacente.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="aa1b8-191">Definizione di un Oracle per effetto sugli stati di base di calcolo</span><span class="sxs-lookup"><span data-stu-id="aa1b8-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="aa1b8-192">È possibile gestire entrambi questi problemi introducendo un secondo registro di $ m $ qubits per fornire la risposta.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="aa1b8-193">Si definirà quindi l'effetto di Oracle su tutti gli Stati di base computazionale: per tutti i $ x \in \\ { 0, 1 \\ } ^ n $ e $ y \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="aa1b8-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="aa1b8-194">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="aa1b8-195">Ora $ o = ^ \dagger $ per costruzione, abbiamo risolto entrambi i problemi precedenti.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="aa1b8-196">>Per vedere che $ o = o ^ { \dagger } $ , si noti che $ o ^ 2 = \boldone $ da $ \oplus b \oplus b = a $ per All $ a, b \in \: :: NO-LOC ({)::: 0, 1 \: :: NO-LOC (})::: $ .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="aa1b8-197">>Di conseguenza, $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="aa1b8-198">In particolare, la definizione di un Oracle in questo modo per ogni stato di base di calcolo $ \ket { x } \ket { y } $ definisce anche il modo $ in cui O $ agisce per qualsiasi altro stato.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="aa1b8-199">Questa operazione segue immediatamente il fatto che $ O $ , come tutte le operazioni Quantum, è lineare nello stato su cui agisce.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="aa1b8-200">Si consideri l'operazione Hadamard, ad esempio, definita da $ h \ket { 0 } = \ket { + } $ e $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="aa1b8-201">Se si vuole ottenere informazioni sulle modalità di funzionamento $ $ di h $ \ket { + } $ , è possibile usare $ h $ è lineare,</span><span class="sxs-lookup"><span data-stu-id="aa1b8-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="aa1b8-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="aa1b8-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="aa1b8-203">&= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="aa1b8-204">In caso di definizione di Oracle $ O $ , è possibile usare in modo analogo che qualsiasi stato $ \ket { \psi } $ in $ n + m $ qubits può essere scritto come</span><span class="sxs-lookup"><span data-stu-id="aa1b8-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="aa1b8-205">\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="aa1b8-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="aa1b8-206">dove $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ rappresenta i coefficienti dello stato $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="aa1b8-207">Pertanto</span><span class="sxs-lookup"><span data-stu-id="aa1b8-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="aa1b8-208">O \ket { \psi } & = o \sum _{ x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum_ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="aa1b8-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="aa1b8-209">&= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="aa1b8-210">Oracle della fase</span><span class="sxs-lookup"><span data-stu-id="aa1b8-210">Phase oracles</span></span>
<span data-ttu-id="aa1b8-211">In alternativa, è possibile codificare $ f $ in un oggetto Oracle $ O $ applicando una _fase_ basata sull'input a $ o $ . Ad esempio, è possibile definire $ O $ tale $$</span><span class="sxs-lookup"><span data-stu-id="aa1b8-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="aa1b8-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="aa1b8-213">Se una fase Oracle agisce inizialmente su un registro in uno stato di base computazionale $ \ket { x } $ , questa fase è una fase globale e pertanto non è osservabile.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="aa1b8-214">Tale Oracle, tuttavia, può essere una risorsa molto potente se applicata a una superposizione o come operazione controllata.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="aa1b8-215">Si consideri, ad esempio, una fase $ O_f Oracle $ per una funzione a qubit singola $ f $ .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="aa1b8-216">Quindi $$</span><span class="sxs-lookup"><span data-stu-id="aa1b8-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="aa1b8-217">O_f \ket{+}</span><span class="sxs-lookup"><span data-stu-id="aa1b8-217">O_f \ket{+}</span></span>
        <span data-ttu-id="aa1b8-218">&=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="aa1b8-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="aa1b8-219">&=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="aa1b8-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="aa1b8-220">&=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="aa1b8-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="aa1b8-221">&=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="aa1b8-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

> [!NOTE]
<span data-ttu-id="aa1b8-222">>Si noti che $ z ^ { -1 } = z ^ { \dagger } = Z $ e quindi $ z ^ { f (0)-f (1) } = z ^ { f (1)-f (0) } .$</span><span class="sxs-lookup"><span data-stu-id="aa1b8-222">> Note that $Z^{-1}=Z^{\dagger}=Z$ and therefore $Z^{f(0)-f(1)}=Z^{f(1)-f(0)}.$</span></span>

<span data-ttu-id="aa1b8-223">Più in generale, entrambe le visualizzazioni di Oracle possono essere ampliate per rappresentare funzioni classiche che restituiscono numeri reali anziché solo un bit singolo.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-223">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="aa1b8-224">La scelta del modo migliore per implementare un Oracle dipende in larga misura dal modo in cui tale Oracle verrà utilizzato all'interno di un determinato algoritmo.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-224">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="aa1b8-225">Ad esempio, l' [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) si basa su Oracle implementato nel primo modo, mentre l' [algoritmo di Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) si basa su Oracle implementato nel secondo modo.</span><span class="sxs-lookup"><span data-stu-id="aa1b8-225">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="aa1b8-226">Per altri dettagli, è consigliabile discutere in [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="aa1b8-226">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
