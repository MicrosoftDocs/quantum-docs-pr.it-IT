---
<span data-ttu-id="b083b-101">Titolo: Pauli Measurements Description: informazioni su come usare le operazioni di misurazione di Pauli a qubit singolo e a più livelli.</span><span class="sxs-lookup"><span data-stu-id="b083b-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="b083b-102">autore: QuantumWriter UID: Microsoft. Quantum. Concepts. Pauli ms. Author: nawiebe@microsoft.com ms. Date: 12/11/2017 ms. Topic: article no-loc:</span><span class="sxs-lookup"><span data-stu-id="b083b-102">author: QuantumWriter uid: microsoft.quantum.concepts.pauli ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="b083b-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="b083b-103">"Q#"</span></span>
- <span data-ttu-id="b083b-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="b083b-104">"$$v"</span></span>
- <span data-ttu-id="b083b-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="b083b-105">"$$"</span></span>
- <span data-ttu-id="b083b-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="b083b-106">"$$"</span></span>
- <span data-ttu-id="b083b-107">"$"</span><span class="sxs-lookup"><span data-stu-id="b083b-107">"$"</span></span>
- <span data-ttu-id="b083b-108">"$"</span><span class="sxs-lookup"><span data-stu-id="b083b-108">"$"</span></span>
- <span data-ttu-id="b083b-109">"$"</span><span class="sxs-lookup"><span data-stu-id="b083b-109">"$"</span></span>
- <span data-ttu-id="b083b-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="b083b-110">"$$"</span></span>
- <span data-ttu-id="b083b-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="b083b-111">"\cdots"</span></span>
- <span data-ttu-id="b083b-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="b083b-112">"bmatrix"</span></span>
- <span data-ttu-id="b083b-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="b083b-113">"\ddots"</span></span>
- <span data-ttu-id="b083b-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="b083b-114">"\equiv"</span></span>
- <span data-ttu-id="b083b-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="b083b-115">"\sum"</span></span>
- <span data-ttu-id="b083b-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="b083b-116">"\begin"</span></span>
- <span data-ttu-id="b083b-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="b083b-117">"\end"</span></span>
- <span data-ttu-id="b083b-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="b083b-118">"\sqrt"</span></span>
- <span data-ttu-id="b083b-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="b083b-119">"\otimes"</span></span>
- <span data-ttu-id="b083b-120">"{"</span><span class="sxs-lookup"><span data-stu-id="b083b-120">"{"</span></span>
- <span data-ttu-id="b083b-121">"}"</span><span class="sxs-lookup"><span data-stu-id="b083b-121">"}"</span></span>
- <span data-ttu-id="b083b-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="b083b-122">"\text"</span></span>
- <span data-ttu-id="b083b-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="b083b-123">"\phi"</span></span>
- <span data-ttu-id="b083b-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="b083b-124">"\kappa"</span></span>
- <span data-ttu-id="b083b-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="b083b-125">"\psi"</span></span>
- <span data-ttu-id="b083b-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="b083b-126">"\alpha"</span></span>
- <span data-ttu-id="b083b-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="b083b-127">"\beta"</span></span>
- <span data-ttu-id="b083b-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="b083b-128">"\gamma"</span></span>
- <span data-ttu-id="b083b-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="b083b-129">"\delta"</span></span>
- <span data-ttu-id="b083b-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="b083b-130">"\omega"</span></span>
- <span data-ttu-id="b083b-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="b083b-131">"\bra"</span></span>
- <span data-ttu-id="b083b-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="b083b-132">"\ket"</span></span>
- <span data-ttu-id="b083b-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="b083b-133">"\boldone"</span></span>
- <span data-ttu-id="b083b-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="b083b-134">"\\\\"</span></span>
- <span data-ttu-id="b083b-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="b083b-135">"\\"</span></span>
- <span data-ttu-id="b083b-136">"="</span><span class="sxs-lookup"><span data-stu-id="b083b-136">"="</span></span>
- <span data-ttu-id="b083b-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="b083b-137">"\frac"</span></span>
- <span data-ttu-id="b083b-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="b083b-138">"\text"</span></span>
- <span data-ttu-id="b083b-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="b083b-139">"\mapsto"</span></span>
- <span data-ttu-id="b083b-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="b083b-140">"\dagger"</span></span>
- <span data-ttu-id="b083b-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="b083b-141">"\to"</span></span>
- <span data-ttu-id="b083b-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="b083b-142">"\begin{cases}"</span></span>
- <span data-ttu-id="b083b-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="b083b-143">"\end{cases}"</span></span>
- <span data-ttu-id="b083b-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="b083b-144">"\operatorname"</span></span>
- <span data-ttu-id="b083b-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="b083b-145">"\braket"</span></span>
- <span data-ttu-id="b083b-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="b083b-146">"\id"</span></span>
- <span data-ttu-id="b083b-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="b083b-147">"\expect"</span></span>
- <span data-ttu-id="b083b-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="b083b-148">"\defeq"</span></span>
- <span data-ttu-id="b083b-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="b083b-149">"\variance"</span></span>
- <span data-ttu-id="b083b-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="b083b-150">"\dd"</span></span>
- <span data-ttu-id="b083b-151">"&"</span><span class="sxs-lookup"><span data-stu-id="b083b-151">"&"</span></span>
- <span data-ttu-id="b083b-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="b083b-152">"\begin{align}"</span></span>
- <span data-ttu-id="b083b-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="b083b-153">"\end{align}"</span></span>
- <span data-ttu-id="b083b-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="b083b-154">"\Lambda"</span></span>
- <span data-ttu-id="b083b-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="b083b-155">"\lambda"</span></span>
- <span data-ttu-id="b083b-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="b083b-156">"\Omega"</span></span>
- <span data-ttu-id="b083b-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="b083b-157">"\mathrm"</span></span>
- <span data-ttu-id="b083b-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="b083b-158">"\left"</span></span>
- <span data-ttu-id="b083b-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="b083b-159">"\right"</span></span>
- <span data-ttu-id="b083b-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="b083b-160">"\qquad"</span></span>
- <span data-ttu-id="b083b-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="b083b-161">"\times"</span></span>
- <span data-ttu-id="b083b-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="b083b-162">"\big"</span></span>
- <span data-ttu-id="b083b-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="b083b-163">"\langle"</span></span>
- <span data-ttu-id="b083b-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="b083b-164">"\rangle"</span></span>
- <span data-ttu-id="b083b-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="b083b-165">"\bigg"</span></span>
- <span data-ttu-id="b083b-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="b083b-166">"\Big"</span></span>
- <span data-ttu-id="b083b-167">"|"</span><span class="sxs-lookup"><span data-stu-id="b083b-167">"|"</span></span>
- <span data-ttu-id="b083b-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="b083b-168">"\mathbb"</span></span>
- <span data-ttu-id="b083b-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="b083b-169">"\vec"</span></span>
- <span data-ttu-id="b083b-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="b083b-170">"\in"</span></span>
- <span data-ttu-id="b083b-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="b083b-171">"\texttt"</span></span>
- <span data-ttu-id="b083b-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="b083b-172">"\ne"</span></span>
- <span data-ttu-id="b083b-173">"<"</span><span class="sxs-lookup"><span data-stu-id="b083b-173">"<"</span></span>
- <span data-ttu-id="b083b-174">">"</span><span class="sxs-lookup"><span data-stu-id="b083b-174">">"</span></span>
- <span data-ttu-id="b083b-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="b083b-175">"\leq"</span></span>
- <span data-ttu-id="b083b-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="b083b-176">"\geq"</span></span>
- <span data-ttu-id="b083b-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="b083b-177">"~~"</span></span>
- <span data-ttu-id="b083b-178">"~"</span><span class="sxs-lookup"><span data-stu-id="b083b-178">"~"</span></span>
- <span data-ttu-id="b083b-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="b083b-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="b083b-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="b083b-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="b083b-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="b083b-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="b083b-182">Misurazioni di Pauli</span><span class="sxs-lookup"><span data-stu-id="b083b-182">Pauli Measurements</span></span>

<span data-ttu-id="b083b-183">Nelle discussioni precedenti sono state illustrate le misure di base computazionali.</span><span class="sxs-lookup"><span data-stu-id="b083b-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="b083b-184">In realtà, esistono altre misure comuni che si verificano in quantum computing che, dal punto di vista della notazione, sono utili per esprimere in termini di misurazioni di base computazionale.</span><span class="sxs-lookup"><span data-stu-id="b083b-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="b083b-185">Quando si lavora con Q# , il tipo di misurazioni più comune che verrà eseguito sarà probabilmente costituito dalle *misurazioni di Pauli*, che generalizzano le misurazioni di base computazionali per includere le misurazioni in altre basi e la parità tra qubits diversi.</span><span class="sxs-lookup"><span data-stu-id="b083b-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="b083b-186">In questi casi, è comune discutere la misurazione di un operatore Pauli, in generale un operatore come $ x, Y, z $ o $ z \otimes z, x \otimes x, x \otimes Y $ e così via.</span><span class="sxs-lookup"><span data-stu-id="b083b-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
<span data-ttu-id="b083b-187">>In Q# gli operatori Pauli multiqubit sono in genere rappresentati da matrici di tipo `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="b083b-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="b083b-188">>Ad esempio, per rappresentare $ X \otimes Z \otimes Y $ , è possibile usare la matrice `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="b083b-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="b083b-189">La discussione sulla misurazione in termini di operatori Pauli è particolarmente comune nel sottocampo della correzione degli errori quantistici.</span><span class="sxs-lookup"><span data-stu-id="b083b-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="b083b-190">In Q# si segue una convenzione simile, che ora spiega questa visualizzazione alternativa delle misurazioni.</span><span class="sxs-lookup"><span data-stu-id="b083b-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="b083b-191">Prima di approfondire i dettagli su come pensare a una misurazione di Pauli, è utile considerare la misurazione di un singolo qubit all'interno di un computer Quantum allo stato quantum.</span><span class="sxs-lookup"><span data-stu-id="b083b-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="b083b-192">Si supponga di avere uno $ $ stato quantum n-qubit, quindi la misurazione di un qubit immediatamente regola la metà delle $ 2 ^ n $ possibilità che lo stato potrebbe essere.</span><span class="sxs-lookup"><span data-stu-id="b083b-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="b083b-193">In altre parole, la misurazione proietta lo stato del quantum su uno dei due spazi.</span><span class="sxs-lookup"><span data-stu-id="b083b-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="b083b-194">Possiamo generalizzare il modo in cui pensiamo alla misurazione per riflettere questa intuizione.</span><span class="sxs-lookup"><span data-stu-id="b083b-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="b083b-195">Per identificare in modo conciso questi spazi, è necessario un linguaggio per descriverli.</span><span class="sxs-lookup"><span data-stu-id="b083b-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="b083b-196">Per descrivere i due sottospazi, è possibile specificarli tramite una matrice in cui sono presenti solo due autovalori univoci, presi dalla Convenzione come $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="b083b-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="b083b-197">Per un semplice esempio di descrizione di sottospazi in questo modo, prendere in considerazione $ Z $ :</span><span class="sxs-lookup"><span data-stu-id="b083b-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="b083b-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="b083b-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="b083b-199">Leggendo gli elementi diagonali della matrice Pauli- $ Z $ , è possibile osservare che la $ Z $ ha due autovettori, $ \ket { 0 } $ e $ \ket { 1 } $ , con gli autovalori corrispondenti $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="b083b-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="b083b-200">Quindi, se misuriamo il qubit e otteniamo `Zero` (corrispondente allo stato $ \ket { 0 } $ ), sappiamo che lo stato del qubit è a $ + 1 $ autostato dell' $ $ operatore Z.</span><span class="sxs-lookup"><span data-stu-id="b083b-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="b083b-201">Analogamente, se si ottiene `One` , sappiamo che lo stato del qubit è $ -1 $ autostato $ Z $ . Questo processo viene definito nel linguaggio delle misurazioni di Pauli come "misurazione di Pauli $ Z $ " ed è completamente equivalente all'esecuzione di una misurazione di base computazionale.</span><span class="sxs-lookup"><span data-stu-id="b083b-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="b083b-202">Qualsiasi $ \times matrice 2 2 $ che rappresenta una trasformazione unitaria di $ Z $ soddisfa anche questo criterio.</span><span class="sxs-lookup"><span data-stu-id="b083b-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="b083b-203">È anche possibile usare una matrice $ a = u ^ \dagger Z u $ , dove $ u $ è qualsiasi altra matrice unitaria, per assegnare a una matrice la definizione dei due risultati di una misura nel $ \pm 1 $ autovettori.</span><span class="sxs-lookup"><span data-stu-id="b083b-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="b083b-204">La notazione delle misurazioni di Pauli fa riferimento a questa equivalenza unitaria identificando le $ misurazioni X, Y, Z $ come misurazioni equivalenti che possono essere eseguite per ottenere informazioni da un qubit.</span><span class="sxs-lookup"><span data-stu-id="b083b-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="b083b-205">Queste misurazioni sono fornite di seguito per praticità.</span><span class="sxs-lookup"><span data-stu-id="b083b-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="b083b-206">|Trasformazione unità di misura Pauli ||</span><span class="sxs-lookup"><span data-stu-id="b083b-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="b083b-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="b083b-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="b083b-208">|$ $ X | $H               $                    |</span><span class="sxs-lookup"><span data-stu-id="b083b-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="b083b-209">|$ $ Y | $HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="b083b-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="b083b-210">Ovvero, usando questo linguaggio, "Measure $ Y $ " equivale a applicare $ HS ^ \dagger $ e quindi a misurare la base di calcolo, dove [`S`](xref:microsoft.quantum.intrinsic.s) è un'operazione Quantum intrinseca talvolta denominata "Phase Gate" e può essere simulata dalla matrice unitaria.</span><span class="sxs-lookup"><span data-stu-id="b083b-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="b083b-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="b083b-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="b083b-212">1 & 0 \\\\ 0 & i \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="b083b-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="b083b-213">Equivale anche all'applicazione di $ HS ^ \dagger $ al vettore di stato quantum e alla misurazione $ della Z $ , in modo che l'operazione seguente sia equivalente a `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="b083b-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="b083b-214">Lo stato corretto viene quindi trovato trasformando di nuovo in base al calcolo, che equivale a applicare $ sh $ al vettore di stato quantum. nel frammento di codice precedente, la trasformazione alla base computazionale viene gestita automaticamente dall'utilizzo del `within … apply` blocco.</span><span class="sxs-lookup"><span data-stu-id="b083b-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="b083b-215">In Q# si dice il risultato---ovvero le informazioni classiche estratte dall'interazione con lo stato---sono fornite da un `Result` valore $ j \in \\ { \texttt { zero } , uno che \texttt { } \\ } $ indica se il risultato è in $ (-1) ^ j $ eigenspace dell'operatore Pauli misurato.</span><span class="sxs-lookup"><span data-stu-id="b083b-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="b083b-216">Misurazioni a più qubit</span><span class="sxs-lookup"><span data-stu-id="b083b-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="b083b-217">Le misurazioni degli operatori qubit di Pauli sono definite in modo analogo, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b083b-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="b083b-218">Z \otimes z = \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & -1 & 0 & 0 \\\\ 0 & 0 & -1 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="b083b-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="b083b-219">Di conseguenza, i prodotti tensore di due operatori Pauli- $ Z $ formano una matrice costituita da due spazi costituiti da $ + 1 $ e $ -1 $ autovalori.</span><span class="sxs-lookup"><span data-stu-id="b083b-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="b083b-220">Come nel caso di un singolo qubit, entrambe costituiscono un mezzo di spazio che significa che la metà dello spazio vettoriale accessibile appartiene a $ + 1 $ eigenspace e la metà rimanente a $ -1 $ eigenspace.</span><span class="sxs-lookup"><span data-stu-id="b083b-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="b083b-221">In generale, è facile vedere dalla definizione del prodotto tensore che tutti i prodotti tensori degli operatori Pauli- $ Z $ e l'identità rispettano questo problema.</span><span class="sxs-lookup"><span data-stu-id="b083b-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="b083b-222">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b083b-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="b083b-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="b083b-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="b083b-224">1 & 0 & 0 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="b083b-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="b083b-225">0 & 1 & 0 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="b083b-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="b083b-226">0 & 0 & -1 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="b083b-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="b083b-227">0 & 0 & 0 & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="b083b-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="b083b-228">Come prima, eventuali trasformazioni unitarie di tali matrici descrivono anche due spazi con etichetta $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="b083b-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="b083b-229">Ad esempio, $ x \otimes x = h h \otimes (z \otimes z) h \otimes h $ dall'identità $ = HxH z $ .</span><span class="sxs-lookup"><span data-stu-id="b083b-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="b083b-230">Analogamente al caso qubit, tutte le qubit di tipo Pauli possono essere scritte come $ u ^ \dagger (Z \otimes \id ) u $ per $ 4 \times $ matrici unitarie $ u $ . Le trasformazioni vengono enumerate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b083b-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="b083b-231">>Nella tabella seguente si usa $ \operatorname { swap } $ per indicare la matrice >$$</span><span class="sxs-lookup"><span data-stu-id="b083b-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="b083b-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="b083b-232">> \begin{align}</span></span>
<span data-ttu-id="b083b-233">>     \operatorname{Scambia } &=</span><span class="sxs-lookup"><span data-stu-id="b083b-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="b083b-234">>     \left( \begin { matrice}</span><span class="sxs-lookup"><span data-stu-id="b083b-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="b083b-235">>1 & 0 & 0 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="b083b-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="b083b-236">>0 & 0 & 1 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="b083b-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="b083b-237">>0 & 1 & 0 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="b083b-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="b083b-238">>0 & 0 & 0 & 1 > \end { matrice } \right ) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="b083b-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="b083b-239">> $$</span><span class="sxs-lookup"><span data-stu-id="b083b-239">> $$</span></span>
<span data-ttu-id="b083b-240">>utilizzato per simulare l'operazione intrinseca [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="b083b-240">> used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

<span data-ttu-id="b083b-241">|Trasformazione unità di misura Pauli ||</span><span class="sxs-lookup"><span data-stu-id="b083b-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="b083b-242">|$ \otimes \boldone Z $ | $\boldone \otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="b083b-242">| $Z \otimes \boldone$ | $\boldone \otimes \boldone$ |</span></span>
<span data-ttu-id="b083b-243">|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="b083b-243">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="b083b-244">|$ \otimes \boldone X $ | $ \otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="b083b-244">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="b083b-245">|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="b083b-245">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="b083b-246">|$\boldone \otimes $ | $ \operatorname { swap } Z $|</span><span class="sxs-lookup"><span data-stu-id="b083b-246">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="b083b-247">|$\boldone \otimes $ | $ \otimes \boldone \operatorname { swap } X (H $ )|</span><span class="sxs-lookup"><span data-stu-id="b083b-247">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="b083b-248">|$\boldone \otimes $ | $ \dagger \otimes \boldone \operatorname { scambio } Y $ (HS ^)|</span><span class="sxs-lookup"><span data-stu-id="b083b-248">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="b083b-249">|$Z \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="b083b-249">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="b083b-250">|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="b083b-250">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="b083b-251">|$Y \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="b083b-251">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="b083b-252">|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="b083b-252">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="b083b-253">|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="b083b-253">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="b083b-254">|$Y \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="b083b-254">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="b083b-255">|$Z \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="b083b-255">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="b083b-256">|$X \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="b083b-256">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="b083b-257">|$Y \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="b083b-257">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="b083b-258">In questo caso, l' [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operazione viene visualizzata per il motivo seguente.</span><span class="sxs-lookup"><span data-stu-id="b083b-258">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="b083b-259">Ogni misura di Pauli che non include la $ \boldone $ matrice è equivalente al valore di un elemento unitario alla $ z \otimes z $ con la motivazione precedente.</span><span class="sxs-lookup"><span data-stu-id="b083b-259">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="b083b-260">Gli autovalori della $ z \otimes z $ dipendono solo dalla parità dei qubits che comprendono ogni vettore di base computazionale e le operazioni controllate-not servono per calcolare questa parità e archiviarla nel primo bit.</span><span class="sxs-lookup"><span data-stu-id="b083b-260">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="b083b-261">Quindi, una volta misurato il primo bit, è possibile recuperare l'identità dello spazio a metà risultante, equivalente alla misurazione dell'operatore Pauli.</span><span class="sxs-lookup"><span data-stu-id="b083b-261">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="b083b-262">Una nota aggiuntiva: Sebbene sia possibile tentare di presumere che la misura $ z \otimes z $ sia uguale alla misurazione sequenziale di $ z \otimes \mathbb { 1 } $ e quindi di $ \mathbb { 1 } \otimes Z $ , questo presupposto è false.</span><span class="sxs-lookup"><span data-stu-id="b083b-262">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="b083b-263">Il motivo è che la misurazione della $ z \otimes z $ proietta lo stato del quantum in una $ autostato + 1 $ o $ -1 $ di questi operatori.</span><span class="sxs-lookup"><span data-stu-id="b083b-263">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="b083b-264">Se si misura $ z \otimes \mathbb { 1 } $ e poi $ \mathbb { 1 } \otimes z, $ il vettore di stato quantum viene proiettato per primo in una metà dello spazio $ z \otimes \mathbb { 1 } $ e quindi in una metà dello spazio $ \mathbb { 1 } \otimes z $ . Poiché sono presenti quattro vettori di base di calcolo, l'esecuzione di entrambe le misurazioni riduce lo stato a un trimestre e quindi lo riduce a un singolo vettore di base computazionale.</span><span class="sxs-lookup"><span data-stu-id="b083b-264">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="b083b-265">Correlazioni tra qubits</span><span class="sxs-lookup"><span data-stu-id="b083b-265">Correlations between qubits</span></span>
<span data-ttu-id="b083b-266">Un altro modo per esaminare i prodotti tensori di matrici di Pauli come $ x \otimes x $ o $ z \otimes z $ è che queste misurazioni consentono di esaminare le informazioni archiviate nelle correlazioni tra le due qubits.</span><span class="sxs-lookup"><span data-stu-id="b083b-266">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="b083b-267">La misurazione di $ X \otimes \id $ consente di esaminare le informazioni archiviate localmente nel primo qubit.</span><span class="sxs-lookup"><span data-stu-id="b083b-267">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="b083b-268">Sebbene entrambi i tipi di misurazioni siano ugualmente utili nell'elaborazione quantistica, il primo illumina la potenza del quantum computing.</span><span class="sxs-lookup"><span data-stu-id="b083b-268">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="b083b-269">Si rivela che in quantum computing, spesso le informazioni che si desidera apprendere non vengono archiviate in un singolo qubit ma piuttosto archiviate in modo non locale in tutti i qubits in una sola volta e, pertanto, solo esaminando la misura tramite una misurazione congiunta (ad esempio, $ z \otimes z $ ) queste informazioni diventano manifeste.</span><span class="sxs-lookup"><span data-stu-id="b083b-269">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="b083b-270">Nella correzione degli errori, ad esempio, si desidera spesso conoscere l'errore che si è verificato durante l'apprendimento di nulla sullo stato che si sta tentando di proteggere.</span><span class="sxs-lookup"><span data-stu-id="b083b-270">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="b083b-271">Nell' [esempio di codice a scorrimento bit](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) viene illustrato un esempio di come è possibile utilizzare misure come $ z \otimes z \otimes \id $ e $ \id \otimes z \otimes z $ . < --TODO: modificare questo valore in un collegamento al browser degli esempi non appena viene caricato l'esempio di codice di Flip bit.</span><span class="sxs-lookup"><span data-stu-id="b083b-271">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="b083b-272">$ \otimes \otimes \otimes \boldone $ È possibile misurare anche operatori Pauli arbitrari, ad esempio X Y Z.</span><span class="sxs-lookup"><span data-stu-id="b083b-272">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="b083b-273">Tutti questi prodotti tensore di operatori Pauli hanno solo due autovalori $ \pm 1 $ e entrambi eigenspaces costituiscono metà spazi dell'intero spazio vettoriale.</span><span class="sxs-lookup"><span data-stu-id="b083b-273">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="b083b-274">Coincidono quindi con i requisiti indicati sopra.</span><span class="sxs-lookup"><span data-stu-id="b083b-274">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="b083b-275">In Q# , tali misure restituiscono $ j $ se la misurazione restituisce un risultato nel eigenspace di segno $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="b083b-275">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="b083b-276">Il fatto che le misurazioni di Pauli come funzionalità integrate in Q# risulti utile perché la misurazione di tali operatori richiede lunghe catene di controlli e non trasformazioni di base per descrivere il diagonalizing $ U $ Gate necessario per esprimere l'operazione come prodotto tensore $ Z $ e $ \id $ .</span><span class="sxs-lookup"><span data-stu-id="b083b-276">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="b083b-277">Con la possibilità di specificare che si desidera eseguire una di queste misurazioni predefinite, non è necessario preoccuparsi di come trasformare la base in modo che una misura di base computazionale fornisca le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="b083b-277">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="b083b-278">Q#gestisce automaticamente tutte le trasformazioni di base necessarie.</span><span class="sxs-lookup"><span data-stu-id="b083b-278">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="b083b-279">Per ulteriori informazioni, vedere le [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operazioni e.</span><span class="sxs-lookup"><span data-stu-id="b083b-279">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="b083b-280">Teorema di no-cloning</span><span class="sxs-lookup"><span data-stu-id="b083b-280">The No-Cloning Theorem</span></span>

<span data-ttu-id="b083b-281">Le informazioni sul quantum sono potenti.</span><span class="sxs-lookup"><span data-stu-id="b083b-281">Quantum information is powerful.</span></span>
<span data-ttu-id="b083b-282">Ci permette di eseguire operazioni straordinarie, ad esempio numeri di fattore esponenzialmente più veloci rispetto agli algoritmi classici più noti, oppure simulare in modo efficiente i sistemi elettronici correlati che richiedono in genere un costo esponenziale per simulare in modo accurato.</span><span class="sxs-lookup"><span data-stu-id="b083b-282">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="b083b-283">Esistono tuttavia alcune limitazioni alla potenza del quantum computing.</span><span class="sxs-lookup"><span data-stu-id="b083b-283">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="b083b-284">Una limitazione di questo tipo viene fornita dal *teorema di no-cloning*.</span><span class="sxs-lookup"><span data-stu-id="b083b-284">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="b083b-285">Il teorema dell'assenza di clonazione è denominato.</span><span class="sxs-lookup"><span data-stu-id="b083b-285">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="b083b-286">Non consente la clonazione di stati Quantum generici da un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="b083b-286">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="b083b-287">La prova del teorema è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="b083b-287">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="b083b-288">Anche se una prova completa del teorema di non clonazione è un po' troppo tecnica per la nostra discussione, la prova nel caso di nessun qubits ausiliario aggiuntivo si trova all'interno dell'ambito (qubits ausiliari sono qubits utilizzati per lo spazio scratch durante un calcolo e sono facilmente utilizzabili e gestiti in, vedere la pagina relativa a Q# [qubits in prestito](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="b083b-288">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="b083b-289">Per tale computer quantistico, l'operazione di clonazione deve essere descritta da una matrice unitaria.</span><span class="sxs-lookup"><span data-stu-id="b083b-289">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="b083b-290">Non è consentita la misurazione, perché danneggia lo stato del quantum che si sta tentando di clonare.</span><span class="sxs-lookup"><span data-stu-id="b083b-290">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="b083b-291">Per simulare l'operazione di clonazione, è necessario che la matrice unitaria venga utilizzata per la proprietà$$</span><span class="sxs-lookup"><span data-stu-id="b083b-291">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="b083b-292">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="b083b-292">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="b083b-293">per qualsiasi stato $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="b083b-293">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="b083b-294">La proprietà Linearity della moltiplicazione di matrici implica quindi che per qualsiasi secondo stato quantum $ \ket { \phi } $ ,</span><span class="sxs-lookup"><span data-stu-id="b083b-294">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="b083b-295">U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="b083b-295">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="b083b-296">&= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="b083b-296">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="b083b-297">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="b083b-297">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="b083b-298">&= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="b083b-298">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="b083b-299">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="b083b-299">\right) \\\\</span></span>
    <span data-ttu-id="b083b-300">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).</span><span class="sxs-lookup"><span data-stu-id="b083b-300">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="b083b-301">Si tratta di un'intuizione fondamentale dietro il teorema di no-cloning: qualsiasi dispositivo che copia uno stato quantum sconosciuto deve causare errori in almeno alcuni degli stati copiati.</span><span class="sxs-lookup"><span data-stu-id="b083b-301">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="b083b-302">Sebbene il presupposto fondamentale che il Cloner agisca in modo lineare sullo stato di input possa essere violato tramite l'aggiunta e la misurazione di qubits ausiliari, tali interazioni perdono anche le informazioni sul sistema attraverso le statistiche di misurazione e impediscono la clonazione esatta in tali casi.</span><span class="sxs-lookup"><span data-stu-id="b083b-302">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="b083b-303">Per una prova più completa del teorema di non clonazione, vedere [per altre informazioni](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="b083b-303">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="b083b-304">Il teorema di no-cloning è importante per la comprensione qualitativa del quantum computing, perché se è possibile clonare gli Stati Quantum a costo elevato, è possibile ottenere una capacità quasi magica di apprendere dagli Stati Quantum.</span><span class="sxs-lookup"><span data-stu-id="b083b-304">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="b083b-305">In realtà, è possibile violare il principio di incertezza decantato di Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="b083b-305">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="b083b-306">In alternativa, è possibile usare un Cloner ottimale per ottenere un singolo campione da una distribuzione quantistica complessa e apprendere tutti gli elementi che è possibile conoscere per la distribuzione da un solo esempio.</span><span class="sxs-lookup"><span data-stu-id="b083b-306">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="b083b-307">Si tratta di un'operazione analoga a quella di una moneta e all'osservazione delle teste, quindi quando si comunica a un amico il risultato che li risponde "Ah la distribuzione di tale moneta deve essere Bernoulli con $ p = 0.512643 \ ldots $ !".</span><span class="sxs-lookup"><span data-stu-id="b083b-307">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="b083b-308">Un'istruzione di questo tipo non è sensical, perché una certa quantità di informazioni (il risultato delle intestazioni) non è semplicemente in grado di fornire le informazioni necessarie per codificare la distribuzione senza sostanziali informazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="b083b-308">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="b083b-309">In modo analogo, senza informazioni precedenti, non è possibile clonare perfettamente uno stato quantico proprio come non è possibile preparare un insieme di tali monete senza conoscere $ p $ .</span><span class="sxs-lookup"><span data-stu-id="b083b-309">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="b083b-310">Le informazioni non sono gratuite in quantum computing.</span><span class="sxs-lookup"><span data-stu-id="b083b-310">Information is not free in quantum computing.</span></span>
<span data-ttu-id="b083b-311">Ogni qubit misurato fornisce un solo bit di informazioni e il teorema di no-cloning Mostra che non è presente alcuna backdoor che può essere sfruttata per aggirare il compromesso fondamentale tra le informazioni acquisite sul sistema e il disturbo richiamato al suo interno.</span><span class="sxs-lookup"><span data-stu-id="b083b-311">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
