---
<span data-ttu-id="e4d1d-101">title: vettori e matrici in quantum computing Description: informazioni di base sull'uso di vettori e matrici.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="e4d1d-102">autore: QuantumWriter UID: Microsoft. Quantum. Concepts. vectors ms. Author: nawiebe@microsoft.com ms. Date: 12/11/2017 ms. Topic: article no-loc:</span><span class="sxs-lookup"><span data-stu-id="e4d1d-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="e4d1d-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-103">"$$"</span></span>
- <span data-ttu-id="e4d1d-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-104">"$$"</span></span>
- <span data-ttu-id="e4d1d-105">"$"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-105">"$"</span></span>
- <span data-ttu-id="e4d1d-106">"$"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-106">"$"</span></span>
- <span data-ttu-id="e4d1d-107">"$"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-107">"$"</span></span>
- <span data-ttu-id="e4d1d-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-108">"$$"</span></span>
- <span data-ttu-id="e4d1d-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-109">"\cdots"</span></span>
- <span data-ttu-id="e4d1d-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-110">"bmatrix"</span></span>
- <span data-ttu-id="e4d1d-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-111">"\ddots"</span></span>
- <span data-ttu-id="e4d1d-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-112">"\equiv"</span></span>
- <span data-ttu-id="e4d1d-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-113">"\sum"</span></span>
- <span data-ttu-id="e4d1d-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-114">"\begin"</span></span>
- <span data-ttu-id="e4d1d-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-115">"\end"</span></span>
- <span data-ttu-id="e4d1d-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-116">"\sqrt"</span></span>
- <span data-ttu-id="e4d1d-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-117">"\otimes"</span></span>
- <span data-ttu-id="e4d1d-118">"{"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-118">"{"</span></span>
- <span data-ttu-id="e4d1d-119">"}"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-119">"}"</span></span>
- <span data-ttu-id="e4d1d-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-120">"\text"</span></span>
- <span data-ttu-id="e4d1d-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-121">"\phi"</span></span>
- <span data-ttu-id="e4d1d-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-122">"\kappa"</span></span>
- <span data-ttu-id="e4d1d-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-123">"\psi"</span></span>
- <span data-ttu-id="e4d1d-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-124">"\alpha"</span></span>
- <span data-ttu-id="e4d1d-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-125">"\beta"</span></span>
- <span data-ttu-id="e4d1d-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-126">"\gamma"</span></span>
- <span data-ttu-id="e4d1d-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-127">"\delta"</span></span>
- <span data-ttu-id="e4d1d-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-128">"\omega"</span></span>
- <span data-ttu-id="e4d1d-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-129">"\bra"</span></span>
- <span data-ttu-id="e4d1d-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-130">"\ket"</span></span>
- <span data-ttu-id="e4d1d-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-131">"\boldone"</span></span>
- <span data-ttu-id="e4d1d-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-132">"\\\\"</span></span>
- <span data-ttu-id="e4d1d-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-133">"\\"</span></span>
- <span data-ttu-id="e4d1d-134">"="</span><span class="sxs-lookup"><span data-stu-id="e4d1d-134">"="</span></span>
- <span data-ttu-id="e4d1d-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-135">"\frac"</span></span>
- <span data-ttu-id="e4d1d-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-136">"\text"</span></span>
- <span data-ttu-id="e4d1d-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-137">"\mapsto"</span></span>
- <span data-ttu-id="e4d1d-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-138">"\dagger"</span></span>
- <span data-ttu-id="e4d1d-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-139">"\to"</span></span>
- <span data-ttu-id="e4d1d-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-140">"\begin{cases}"</span></span>
- <span data-ttu-id="e4d1d-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-141">"\end{cases}"</span></span>
- <span data-ttu-id="e4d1d-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-142">"\operatorname"</span></span>
- <span data-ttu-id="e4d1d-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-143">"\braket"</span></span>
- <span data-ttu-id="e4d1d-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-144">"\id"</span></span>
- <span data-ttu-id="e4d1d-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-145">"\expect"</span></span>
- <span data-ttu-id="e4d1d-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-146">"\defeq"</span></span>
- <span data-ttu-id="e4d1d-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-147">"\variance"</span></span>
- <span data-ttu-id="e4d1d-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-148">"\dd"</span></span>
- <span data-ttu-id="e4d1d-149">"&"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-149">"&"</span></span>
- <span data-ttu-id="e4d1d-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-150">"\begin{align}"</span></span>
- <span data-ttu-id="e4d1d-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-151">"\end{align}"</span></span>
- <span data-ttu-id="e4d1d-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-152">"\Lambda"</span></span>
- <span data-ttu-id="e4d1d-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-153">"\lambda"</span></span>
- <span data-ttu-id="e4d1d-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-154">"\Omega"</span></span>
- <span data-ttu-id="e4d1d-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-155">"\mathrm"</span></span>
- <span data-ttu-id="e4d1d-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-156">"\left"</span></span>
- <span data-ttu-id="e4d1d-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-157">"\right"</span></span>
- <span data-ttu-id="e4d1d-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-158">"\qquad"</span></span>
- <span data-ttu-id="e4d1d-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-159">"\times"</span></span>
- <span data-ttu-id="e4d1d-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-160">"\big"</span></span>
- <span data-ttu-id="e4d1d-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-161">"\langle"</span></span>
- <span data-ttu-id="e4d1d-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-162">"\rangle"</span></span>
- <span data-ttu-id="e4d1d-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-163">"\bigg"</span></span>
- <span data-ttu-id="e4d1d-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-164">"\Big"</span></span>
- <span data-ttu-id="e4d1d-165">"|"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-165">"|"</span></span>
- <span data-ttu-id="e4d1d-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-166">"\mathbb"</span></span>
- <span data-ttu-id="e4d1d-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-167">"\vec"</span></span>
- <span data-ttu-id="e4d1d-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-168">"\in"</span></span>
- <span data-ttu-id="e4d1d-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-169">"\texttt"</span></span>
- <span data-ttu-id="e4d1d-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-170">"\ne"</span></span>
- <span data-ttu-id="e4d1d-171">"<"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-171">"<"</span></span>
- <span data-ttu-id="e4d1d-172">">"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-172">">"</span></span>
- <span data-ttu-id="e4d1d-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-173">"\leq"</span></span>
- <span data-ttu-id="e4d1d-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-174">"\geq"</span></span>
- <span data-ttu-id="e4d1d-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-175">"~~"</span></span>
- <span data-ttu-id="e4d1d-176">"~"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-176">"~"</span></span>
- <span data-ttu-id="e4d1d-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="e4d1d-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="e4d1d-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="e4d1d-179">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="e4d1d-180">Vettori e matrici</span><span class="sxs-lookup"><span data-stu-id="e4d1d-180">Vectors and Matrices</span></span>

<span data-ttu-id="e4d1d-181">Una certa familiarità con i vettori e le matrici è essenziale per comprendere il quantum computing.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-181">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="e4d1d-182">Viene fornita una breve introduzione e i lettori interessati sono consigliati per leggere un riferimento standard sull'algebra lineare, ad esempio *Strang, G. (1993). Introduzione all'algebra lineare (vol. 3). Wellesley, MA: Wellesley-Cambridge Press* o un riferimento online, ad esempio [algebra lineare](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="e4d1d-182">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="e4d1d-183">Una colonna Vector (o semplicemente [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ della dimensione (o size) $ n $ è una raccolta di $ n $ numeri complessi $ (V_1, v_2, \ldots, v_n) $ disposti come colonna:</span><span class="sxs-lookup"><span data-stu-id="e4d1d-183">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

$$<span data-ttu-id="e4d1d-184">v=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-184">v =\begin{bmatrix}</span></span>
<span data-ttu-id="e4d1d-185">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-185">v_1\\\\</span></span>
<span data-ttu-id="e4d1d-186">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-186">v_2\\\\</span></span>
<span data-ttu-id="e4d1d-187">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-187">\vdots\\\\</span></span>
<span data-ttu-id="e4d1d-188">v_n\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="e4d1d-188">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="e4d1d-189">La norma di un vettore $ v $ è definita come $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-189">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="e4d1d-190">Un vettore viene detto unità Norm (oppure in alternativa viene definito [*vettore di unità*](https://en.wikipedia.org/wiki/Unit_vector)) se la norma è $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-190">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="e4d1d-191">Il [*contiguo di un vettore*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ è indicato come $ v ^ \dagger $ e viene definito come il vettore di riga seguente, dove $ \* $ indica il coniugato complesso,</span><span class="sxs-lookup"><span data-stu-id="e4d1d-191">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

$$<span data-ttu-id="e4d1d-192">\begin{bmatrix}V_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} V_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="e4d1d-192">\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="e4d1d-193">Il modo più comune per moltiplicare due vettori è il [*prodotto interno*](https://en.wikipedia.org/wiki/Inner_product_space), noto anche come prodotto a punti.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-193">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="e4d1d-194">Il prodotto interno fornisce la proiezione di un vettore su un altro e non è utile per descrivere come esprimere un vettore come una somma di altri vettori più semplici.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-194">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="e4d1d-195">Il prodotto interno tra $ u $ e $ v $ , indica $ \left \langle u, v \right \rangle $ è definito come</span><span class="sxs-lookup"><span data-stu-id="e4d1d-195">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
\langle<span data-ttu-id="e4d1d-196">u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-196"> u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="e4d1d-197">Questa notazione consente inoltre la scrittura della norma di un vettore $ v $ come $ \sqrt { \langle v, v \rangle } $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-197">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="e4d1d-198">È possibile moltiplicare un vettore con un numero $ c $ per formare un nuovo vettore le cui voci vengono moltiplicate per $ c $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-198">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="e4d1d-199">È anche possibile aggiungere due vettori $ u $ e $ v $ per formare un nuovo vettore le cui voci sono la somma delle voci di $ u $ e $ v $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-199">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="e4d1d-200">Queste operazioni sono illustrate di seguito:</span><span class="sxs-lookup"><span data-stu-id="e4d1d-200">These operations are depicted below:</span></span>

$$<span data-ttu-id="e4d1d-201">\mathrm{Se } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-201">\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="e4d1d-202">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-202">u_1\\\\</span></span>
<span data-ttu-id="e4d1d-203">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-203">u_2\\\\</span></span>
<span data-ttu-id="e4d1d-204">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-204">\vdots\\\\</span></span>
<span data-ttu-id="e4d1d-205">u_n \end{bmatrix} ~ \mathrm { e}~</span><span class="sxs-lookup"><span data-stu-id="e4d1d-205">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="e4d1d-206">v=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-206">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="e4d1d-207">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-207">v_1\\\\</span></span>
    <span data-ttu-id="e4d1d-208">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-208">v_2\\\\</span></span>
    <span data-ttu-id="e4d1d-209">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-209">\vdots\\\\</span></span>
    <span data-ttu-id="e4d1d-210">v_n \end{bmatrix} , ~ \mathrm { quindi}~</span><span class="sxs-lookup"><span data-stu-id="e4d1d-210">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="e4d1d-211">Au + BV=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-211">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="e4d1d-212">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-212">au_1+bv_1\\\\</span></span>
<span data-ttu-id="e4d1d-213">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-213">au_2+bv_2\\\\</span></span>
<span data-ttu-id="e4d1d-214">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-214">\vdots\\\\</span></span>
<span data-ttu-id="e4d1d-215">au_n + bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-215">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="e4d1d-216">Una [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) di dimensioni $ m \times n $ è una raccolta di $ $ numeri complessi Mn disposti in $ m $ righe e $ n $ colonne, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e4d1d-216">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

$$<span data-ttu-id="e4d1d-217">M=</span><span class="sxs-lookup"><span data-stu-id="e4d1d-217">M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="e4d1d-218">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-218">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="e4d1d-219">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-219">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="e4d1d-220">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-220">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
\end{bmatrix}<span data-ttu-id="e4d1d-221">.$$</span><span class="sxs-lookup"><span data-stu-id="e4d1d-221">.$$</span></span>

<span data-ttu-id="e4d1d-222">Si noti che un vettore della dimensione $ n $ è semplicemente una matrice di dimensioni $ n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-222">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="e4d1d-223">Come per i vettori, è possibile moltiplicare una matrice con un numero $ c $ per ottenere una nuova matrice in cui ogni voce viene moltiplicata con $ c ed è $ possibile aggiungere due matrici con le stesse dimensioni per produrre una nuova matrice le cui voci sono la somma delle rispettive voci delle due matrici.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-223">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="e4d1d-224">Moltiplicazione di matrici e prodotti tensori</span><span class="sxs-lookup"><span data-stu-id="e4d1d-224">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="e4d1d-225">È anche possibile moltiplicare due matrici $ m $ della dimensione $ m \times n $ e $ n $ della dimensione $ n \times p $ per ottenere una nuova matrice $ p $ della dimensione $ m \times p $ come segue:</span><span class="sxs-lookup"><span data-stu-id="e4d1d-225">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="e4d1d-226">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-226">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="e4d1d-227">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-227">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="e4d1d-228">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-228">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="e4d1d-229">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-229">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="e4d1d-230">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2P}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-230">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="e4d1d-231">N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { NP}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-231">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="e4d1d-232">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-232">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="e4d1d-233">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2P}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-233">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="e4d1d-234">P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-234">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="e4d1d-235">dove le voci di $ P $ sono $ P_ { ik } = \sum _j M_ { IJ } N_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-235">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="e4d1d-236">La voce P_ 11, ad esempio, $ { } $ è il prodotto interno della prima riga di $ M $ con la prima colonna di $ N $ . Si noti che poiché un vettore è semplicemente un caso speciale di una matrice, questa definizione si estende alla moltiplicazione dei vettori di matrici.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-236">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="e4d1d-237">Tutte le matrici considerate saranno matrici quadre, in cui il numero di righe e colonne è uguale, o vettori, che corrisponde a $ una sola $ colonna.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-237">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="e4d1d-238">Una matrice quadrata speciale è la [*matrice di identità*](https://en.wikipedia.org/wiki/Identity_matrix), identificata $ \boldone $ , che include tutti i relativi elementi diagonali pari a $ 1 $ e gli elementi rimanenti uguale a $ 0 $ :</span><span class="sxs-lookup"><span data-stu-id="e4d1d-238">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="e4d1d-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="e4d1d-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
~~<span data-ttu-id="e4d1d-241"> \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-241"> \ddots\\\\</span></span>
<span data-ttu-id="e4d1d-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="e4d1d-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="e4d1d-243">Per una matrice quadrata $ a $ , si dice che la matrice $ B $ è la relativa [*inversa*](https://en.wikipedia.org/wiki/Invertible_matrix) se $ AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-243">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="e4d1d-244">L'inverso di una matrice non deve esistere, ma quando esiste è univoco e viene indicato come $ ^ { -1 } $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-244">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="e4d1d-245">Per qualsiasi matrice $ m $ , la trasportazione contigua o coniugata di $ m $ è una matrice $ N $ tale che $ N_ { IJ } = m_ { Ji } ^ \* $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-245">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="e4d1d-246">Il contiguo di $ m $ è in genere indicato $ m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-246">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="e4d1d-247">Si dice che una matrice $ u $ è [*unitaria*](https://en.wikipedia.org/wiki/Unitary_matrix) se $ UU ^ \dagger = u ^ \dagger u = \boldone $ o equivalente, $ u ^ { -1 } = u ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-247">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="e4d1d-248">Probabilmente la proprietà più importante delle matrici unitarie è che conservano la norma di un vettore.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-248">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="e4d1d-249">Questo problema si verifica perché</span><span class="sxs-lookup"><span data-stu-id="e4d1d-249">This happens because</span></span> 

$$<span data-ttu-id="e4d1d-250">\langlev, v ^ v v ^ \rangle = \dagger = \dagger u ^ { -1 } u v v = ^ \dagger u ^ u v u v \dagger = \langle , u v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="e4d1d-250">\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="e4d1d-251">Una matrice $ m $ è detta [*Hermitiane*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $ m = m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-251">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="e4d1d-252">Infine, il [*prodotto tensore*](https://en.wikipedia.org/wiki/Tensor_product) (o prodotto Kronecker) di due matrici $ m $ di dimensione $ m \times n $ e $ n $ di dimensioni $ p \times q $ è una matrice più grande $ p = M \otimes n $ di dimensioni $ MP \times NQ $ ed è ottenuta da $ m $ e $ n $ come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e4d1d-252">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="e4d1d-253">M \otimes N&=</span><span class="sxs-lookup"><span data-stu-id="e4d1d-253">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="e4d1d-254">M_ { 11 } ~~ \cdots ~~ m_ { 1N }\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-254">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="e4d1d-255">M_ { M1 } ~~ \cdots ~~ m_ { MN  }</span><span class="sxs-lookup"><span data-stu-id="e4d1d-255">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="e4d1d-256">N_ { 11 } ~~ \cdots ~~ N_ { 1Q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-256">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="e4d1d-257">N_ { P1 } ~~ \cdots ~~ N_ { PQ}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-257">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="e4d1d-258">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="e4d1d-258">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="e4d1d-259">M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-259">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="e4d1d-260">M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="e4d1d-260">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="e4d1d-261">M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-261">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    \end{bmatrix}<span data-ttu-id="e4d1d-262">.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-262">.</span></span>
\end{align}

<span data-ttu-id="e4d1d-263">Si tratta di una dimostrazione migliore con alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="e4d1d-263">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="e4d1d-264">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="e4d1d-264">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="e4d1d-265">\begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-265">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        \\\\<span data-ttu-id="e4d1d-266">[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-266">[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    =<span data-ttu-id="e4d1d-267">\begin{bmatrix}c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-267"> \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="e4d1d-268">e</span><span class="sxs-lookup"><span data-stu-id="e4d1d-268">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="e4d1d-269">a \ b \\\\ c \ d\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-269">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="e4d1d-270">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-270">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="e4d1d-271">un\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-271">a\begin{bmatrix}</span></span>
    <span data-ttu-id="e4d1d-272">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-272">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="e4d1d-273">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-273">b\begin{bmatrix}</span></span>
    <span data-ttu-id="e4d1d-274">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \\\\<span data-ttu-id="e4d1d-275">[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-275">[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="e4d1d-276">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="e4d1d-277">d\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-277">d\begin{bmatrix}</span></span>
    <span data-ttu-id="e4d1d-278">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e4d1d-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="e4d1d-279">AE-AF \ be \ BF\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-279">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="e4d1d-280">AG \ Ah \ BG \ BH\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-280">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="e4d1d-281">CE \ CF \ de \ DF\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-281">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="e4d1d-282">CG \ ch \ DG \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-282">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="e4d1d-283">Una convenzione di notazione utile finale che circonda i prodotti tensori è che, per qualsiasi vettore $ v $ o matrice $ M $ , $ v ^ { \otimes n } $ o $ m ^ { \otimes n } $ è una mano breve per un $ $ prodotto tensore ripetuto a n riduzioni.</span><span class="sxs-lookup"><span data-stu-id="e4d1d-283">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="e4d1d-284">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e4d1d-284">For example:</span></span>

\begin{align}
&<span data-ttu-id="e4d1d-285">\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\</span><span class="sxs-lookup"><span data-stu-id="e4d1d-285">\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  &<span data-ttu-id="e4d1d-286">\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & 0 & 0 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e4d1d-286">\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
