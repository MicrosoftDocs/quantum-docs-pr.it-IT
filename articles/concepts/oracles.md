---
<span data-ttu-id="fd225-101">title: Quantum Oracles Description: informazioni su come usare e definire Oracle Quantum, black box operazioni usate come input per un altro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="fd225-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="fd225-102">autore: cgranade UID: Microsoft. Quantum. Concepts. Oracles ms. Author: Christopher.Granade@microsoft.com ms. Date: 07/11/2018 ms. Topic: article no-loc:</span><span class="sxs-lookup"><span data-stu-id="fd225-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="fd225-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="fd225-103">"$$"</span></span>
- <span data-ttu-id="fd225-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="fd225-104">"$$"</span></span>
- <span data-ttu-id="fd225-105">"$"</span><span class="sxs-lookup"><span data-stu-id="fd225-105">"$"</span></span>
- <span data-ttu-id="fd225-106">"$"</span><span class="sxs-lookup"><span data-stu-id="fd225-106">"$"</span></span>
- <span data-ttu-id="fd225-107">"$"</span><span class="sxs-lookup"><span data-stu-id="fd225-107">"$"</span></span>
- <span data-ttu-id="fd225-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="fd225-108">"$$"</span></span>
- <span data-ttu-id="fd225-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="fd225-109">"\cdots"</span></span>
- <span data-ttu-id="fd225-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="fd225-110">"bmatrix"</span></span>
- <span data-ttu-id="fd225-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="fd225-111">"\ddots"</span></span>
- <span data-ttu-id="fd225-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="fd225-112">"\equiv"</span></span>
- <span data-ttu-id="fd225-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="fd225-113">"\sum"</span></span>
- <span data-ttu-id="fd225-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="fd225-114">"\begin"</span></span>
- <span data-ttu-id="fd225-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="fd225-115">"\end"</span></span>
- <span data-ttu-id="fd225-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="fd225-116">"\sqrt"</span></span>
- <span data-ttu-id="fd225-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="fd225-117">"\otimes"</span></span>
- <span data-ttu-id="fd225-118">"{"</span><span class="sxs-lookup"><span data-stu-id="fd225-118">"{"</span></span>
- <span data-ttu-id="fd225-119">"}"</span><span class="sxs-lookup"><span data-stu-id="fd225-119">"}"</span></span>
- <span data-ttu-id="fd225-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="fd225-120">"\text"</span></span>
- <span data-ttu-id="fd225-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="fd225-121">"\phi"</span></span>
- <span data-ttu-id="fd225-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="fd225-122">"\kappa"</span></span>
- <span data-ttu-id="fd225-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="fd225-123">"\psi"</span></span>
- <span data-ttu-id="fd225-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="fd225-124">"\alpha"</span></span>
- <span data-ttu-id="fd225-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="fd225-125">"\beta"</span></span>
- <span data-ttu-id="fd225-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="fd225-126">"\gamma"</span></span>
- <span data-ttu-id="fd225-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="fd225-127">"\delta"</span></span>
- <span data-ttu-id="fd225-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="fd225-128">"\omega"</span></span>
- <span data-ttu-id="fd225-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="fd225-129">"\bra"</span></span>
- <span data-ttu-id="fd225-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="fd225-130">"\ket"</span></span>
- <span data-ttu-id="fd225-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="fd225-131">"\boldone"</span></span>
- <span data-ttu-id="fd225-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="fd225-132">"\\\\"</span></span>
- <span data-ttu-id="fd225-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="fd225-133">"\\"</span></span>
- <span data-ttu-id="fd225-134">"="</span><span class="sxs-lookup"><span data-stu-id="fd225-134">"="</span></span>
- <span data-ttu-id="fd225-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="fd225-135">"\frac"</span></span>
- <span data-ttu-id="fd225-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="fd225-136">"\text"</span></span>
- <span data-ttu-id="fd225-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="fd225-137">"\mapsto"</span></span>
- <span data-ttu-id="fd225-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="fd225-138">"\dagger"</span></span>
- <span data-ttu-id="fd225-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="fd225-139">"\to"</span></span>
- <span data-ttu-id="fd225-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="fd225-140">"\begin{cases}"</span></span>
- <span data-ttu-id="fd225-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="fd225-141">"\end{cases}"</span></span>
- <span data-ttu-id="fd225-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="fd225-142">"\operatorname"</span></span>
- <span data-ttu-id="fd225-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="fd225-143">"\braket"</span></span>
- <span data-ttu-id="fd225-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="fd225-144">"\id"</span></span>
- <span data-ttu-id="fd225-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="fd225-145">"\expect"</span></span>
- <span data-ttu-id="fd225-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="fd225-146">"\defeq"</span></span>
- <span data-ttu-id="fd225-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="fd225-147">"\variance"</span></span>
- <span data-ttu-id="fd225-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="fd225-148">"\dd"</span></span>
- <span data-ttu-id="fd225-149">"&"</span><span class="sxs-lookup"><span data-stu-id="fd225-149">"&"</span></span>
- <span data-ttu-id="fd225-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="fd225-150">"\begin{align}"</span></span>
- <span data-ttu-id="fd225-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="fd225-151">"\end{align}"</span></span>
- <span data-ttu-id="fd225-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="fd225-152">"\Lambda"</span></span>
- <span data-ttu-id="fd225-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="fd225-153">"\lambda"</span></span>
- <span data-ttu-id="fd225-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="fd225-154">"\Omega"</span></span>
- <span data-ttu-id="fd225-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="fd225-155">"\mathrm"</span></span>
- <span data-ttu-id="fd225-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="fd225-156">"\left"</span></span>
- <span data-ttu-id="fd225-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="fd225-157">"\right"</span></span>
- <span data-ttu-id="fd225-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="fd225-158">"\qquad"</span></span>
- <span data-ttu-id="fd225-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="fd225-159">"\times"</span></span>
- <span data-ttu-id="fd225-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="fd225-160">"\big"</span></span>
- <span data-ttu-id="fd225-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="fd225-161">"\langle"</span></span>
- <span data-ttu-id="fd225-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="fd225-162">"\rangle"</span></span>
- <span data-ttu-id="fd225-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="fd225-163">"\bigg"</span></span>
- <span data-ttu-id="fd225-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="fd225-164">"\Big"</span></span>
- <span data-ttu-id="fd225-165">"|"</span><span class="sxs-lookup"><span data-stu-id="fd225-165">"|"</span></span>
- <span data-ttu-id="fd225-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="fd225-166">"\mathbb"</span></span>
- <span data-ttu-id="fd225-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="fd225-167">"\vec"</span></span>
- <span data-ttu-id="fd225-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="fd225-168">"\in"</span></span>
- <span data-ttu-id="fd225-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="fd225-169">"\texttt"</span></span>
- <span data-ttu-id="fd225-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="fd225-170">"\ne"</span></span>
- <span data-ttu-id="fd225-171">"<"</span><span class="sxs-lookup"><span data-stu-id="fd225-171">"<"</span></span>
- <span data-ttu-id="fd225-172">">"</span><span class="sxs-lookup"><span data-stu-id="fd225-172">">"</span></span>
- <span data-ttu-id="fd225-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="fd225-173">"\leq"</span></span>
- <span data-ttu-id="fd225-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="fd225-174">"\geq"</span></span>
- <span data-ttu-id="fd225-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="fd225-175">"~~"</span></span>
- <span data-ttu-id="fd225-176">"~"</span><span class="sxs-lookup"><span data-stu-id="fd225-176">"~"</span></span>
- <span data-ttu-id="fd225-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="fd225-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="fd225-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="fd225-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="fd225-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="fd225-179">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="fd225-180">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="fd225-180">Quantum Oracles</span></span>

<span data-ttu-id="fd225-181">Un $ O Oracle $ è un'operazione "black box" utilizzata come input per un altro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="fd225-181">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="fd225-182">Spesso, tali operazioni vengono definite utilizzando una funzione classica $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ che accetta un $ $ input binario a n bit e produce un $ $ output binario a m bit.</span><span class="sxs-lookup"><span data-stu-id="fd225-182">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="fd225-183">A tale scopo, si consideri un particolare input binario $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="fd225-183">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="fd225-184">È possibile etichettare gli Stati qubit come $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="fd225-184">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="fd225-185">Si può prima di tutto tentare di definire $ o in $ modo che $ o \ket { x } = \ket { f (x) } $ , ma si siano verificati alcuni problemi.</span><span class="sxs-lookup"><span data-stu-id="fd225-185">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="fd225-186">Per prima cosa, $ f $ potrebbe avere dimensioni diverse di input e output ( $ n \ne m $ ), in modo che l'applicazione di $ O $ modifichi il numero di qubits nel registro.</span><span class="sxs-lookup"><span data-stu-id="fd225-186">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="fd225-187">In secondo luogo, anche se $ n = m $ , la funzione non può essere invertibile: se $ f (x) = f (y) $ per alcuni $ x \ne y $ , $ o \ket { x } = o \ket { y } $ ma $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="fd225-187">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="fd225-188">Ciò significa che non sarà possibile costruire l'operazione contigua $ O ^ \dagger $ e per i Oracle è necessario che sia definito un oggetto adiacente.</span><span class="sxs-lookup"><span data-stu-id="fd225-188">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="fd225-189">Definizione di un Oracle per effetto sugli stati di base di calcolo</span><span class="sxs-lookup"><span data-stu-id="fd225-189">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="fd225-190">È possibile gestire entrambi questi problemi introducendo un secondo registro di $ m $ qubits per fornire la risposta.</span><span class="sxs-lookup"><span data-stu-id="fd225-190">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="fd225-191">Si definirà quindi l'effetto di Oracle su tutti gli Stati di base computazionale: per tutti i $ x \in \\ { 0, 1 \\ } ^ n $ e $ y \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="fd225-191">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="fd225-192">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="fd225-192">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="fd225-193">Ora $ o = ^ \dagger $ per costruzione, abbiamo risolto entrambi i problemi precedenti.</span><span class="sxs-lookup"><span data-stu-id="fd225-193">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
><span data-ttu-id="fd225-194">Per vedere che $ o = o ^ { \dagger } $ , si noti che $ o ^ 2 = \boldone $ da $ un \oplus b \oplus b = a $ per tutti i $ , b \in \[ ! OP. NO-LOC ({)] 0, 1 \[ ! OP. NO-LOC (})] $ .</span><span class="sxs-lookup"><span data-stu-id="fd225-194"> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
><span data-ttu-id="fd225-195">Di conseguenza, $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="fd225-195"> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="fd225-196">In particolare, la definizione di un Oracle in questo modo per ogni stato di base di calcolo $ \ket { x } \ket { y } $ definisce anche il modo $ in cui O $ agisce per qualsiasi altro stato.</span><span class="sxs-lookup"><span data-stu-id="fd225-196">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="fd225-197">Questa operazione segue immediatamente il fatto che $ O $ , come tutte le operazioni Quantum, è lineare nello stato su cui agisce.</span><span class="sxs-lookup"><span data-stu-id="fd225-197">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="fd225-198">Si consideri l'operazione Hadamard, ad esempio, definita da $ h \ket { 0 } = \ket { + } $ e $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="fd225-198">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="fd225-199">Se si vuole ottenere informazioni sulle modalità di funzionamento $ $ di h $ \ket { + } $ , è possibile usare $ h $ è lineare,</span><span class="sxs-lookup"><span data-stu-id="fd225-199">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="fd225-200">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="fd225-200">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           &<span data-ttu-id="fd225-201">= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="fd225-201"> = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="fd225-202">In caso di definizione di Oracle $ O $ , è possibile usare in modo analogo che qualsiasi stato $ \ket { \psi } $ in $ n + m $ qubits può essere scritto come</span><span class="sxs-lookup"><span data-stu-id="fd225-202">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
\ket<span data-ttu-id="fd225-203">{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="fd225-203">{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="fd225-204">dove $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ rappresenta i coefficienti dello stato $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="fd225-204">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="fd225-205">Pertanto</span><span class="sxs-lookup"><span data-stu-id="fd225-205">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="fd225-206">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="fd225-206">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             &<span data-ttu-id="fd225-207">= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="fd225-207"> = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="fd225-208">Oracle della fase</span><span class="sxs-lookup"><span data-stu-id="fd225-208">Phase oracles</span></span>
<span data-ttu-id="fd225-209">In alternativa, è possibile codificare $ f $ in un oggetto Oracle $ O $ applicando una _fase_ basata sull'input a $ o $ . Ad esempio, è possibile definire $ O $ tale$$</span><span class="sxs-lookup"><span data-stu-id="fd225-209">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="fd225-210">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="fd225-210">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="fd225-211">Se una fase Oracle agisce inizialmente su un registro in uno stato di base computazionale $ \ket { x } $ , questa fase è una fase globale e pertanto non è osservabile.</span><span class="sxs-lookup"><span data-stu-id="fd225-211">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="fd225-212">Tale Oracle, tuttavia, può essere una risorsa molto potente se applicata a una superposizione o come operazione controllata.</span><span class="sxs-lookup"><span data-stu-id="fd225-212">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="fd225-213">Si consideri, ad esempio, una fase $ O_f Oracle $ per una funzione a qubit singola $ f $ .</span><span class="sxs-lookup"><span data-stu-id="fd225-213">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="fd225-214">Quindi$$</span><span class="sxs-lookup"><span data-stu-id="fd225-214">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="fd225-215">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="fd225-215">O_f \ket{+}</span></span>
        &<span data-ttu-id="fd225-216">=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="fd225-216"> = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="fd225-217">=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="fd225-217"> = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="fd225-218">=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="fd225-218"> = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="fd225-219">=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="fd225-219"> = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="fd225-220">Più in generale, entrambe le visualizzazioni di Oracle possono essere ampliate per rappresentare funzioni classiche che restituiscono numeri reali anziché solo un bit singolo.</span><span class="sxs-lookup"><span data-stu-id="fd225-220">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="fd225-221">La scelta del modo migliore per implementare un Oracle dipende in larga misura dal modo in cui tale Oracle verrà utilizzato all'interno di un determinato algoritmo.</span><span class="sxs-lookup"><span data-stu-id="fd225-221">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="fd225-222">Ad esempio, l' [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) si basa su Oracle implementato nel primo modo, mentre l' [algoritmo di Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) si basa su Oracle implementato nel secondo modo.</span><span class="sxs-lookup"><span data-stu-id="fd225-222">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="fd225-223">Per altri dettagli, è consigliabile discutere in [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="fd225-223">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
