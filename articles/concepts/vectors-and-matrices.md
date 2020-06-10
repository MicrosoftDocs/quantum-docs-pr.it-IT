---
title: Vettori e matrici nel calcolo quantistico
description: Informazioni di base su come usare vettori e matrici.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
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
ms.openlocfilehash: 6c09531cd8bee8f5efb472c95c575daed04d3040
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630196"
---
# <a name="vectors-and-matrices"></a><span data-ttu-id="3351b-103">Vettori e matrici</span><span class="sxs-lookup"><span data-stu-id="3351b-103">Vectors and Matrices</span></span>

<span data-ttu-id="3351b-104">Una certa familiarità con i vettori e le matrici è essenziale per comprendere il quantum computing.</span><span class="sxs-lookup"><span data-stu-id="3351b-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="3351b-105">Viene fornita una breve introduzione e i lettori interessati sono consigliati per leggere un riferimento standard sull'algebra lineare, ad esempio *Strang, G. (1993). Introduzione all'algebra lineare (vol. 3). Wellesley, MA: Wellesley-Cambridge Press* o un riferimento online, ad esempio [algebra lineare](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="3351b-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="3351b-106">Un vettore di colonna (o semplicemente [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ di dimensione (o dimensioni) $n $ è una raccolta di $n $ numeri complessi $ (V_1, v_2, \ldots, v_n) $ disposti come colonna:</span><span class="sxs-lookup"><span data-stu-id="3351b-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="3351b-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="3351b-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-108">v_1\\\\</span></span>
<span data-ttu-id="3351b-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-109">v_2\\\\</span></span>
<span data-ttu-id="3351b-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-110">\vdots\\\\</span></span>
<span data-ttu-id="3351b-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="3351b-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="3351b-112">La norma di un $v vettoriale $ è definita come $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $.</span><span class="sxs-lookup"><span data-stu-id="3351b-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="3351b-113">Un vettore viene detto unità Norm (oppure in alternativa è denominato [*vettore di unità*](https://en.wikipedia.org/wiki/Unit_vector)) se la norma è $1 $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="3351b-114">L'oggetto [*contiguo di un $v vettoriale*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ è indicato $v ^ \dagger $ e viene definito come il vettore di riga seguente, dove $ \* $ indica il coniugato complesso,</span><span class="sxs-lookup"><span data-stu-id="3351b-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="3351b-115">$ $ \begin{ bmatrix } V_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } V_1 ^ \* & \cdots & v_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="3351b-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="3351b-116">Il modo più comune per moltiplicare due vettori è il [*prodotto interno*](https://en.wikipedia.org/wiki/Inner_product_space), noto anche come prodotto a punti.</span><span class="sxs-lookup"><span data-stu-id="3351b-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="3351b-117">Il prodotto interno fornisce la proiezione di un vettore su un altro e non è utile per descrivere come esprimere un vettore come una somma di altri vettori più semplici.</span><span class="sxs-lookup"><span data-stu-id="3351b-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="3351b-118">Il prodotto interno tra $u $ e $v $ , indicato $ \left \langle u, v \right \rangle $ è definito come</span><span class="sxs-lookup"><span data-stu-id="3351b-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="3351b-119">$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="3351b-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="3351b-120">Questa notazione consente inoltre di scrivere la norma di un vettore $v $ come $ \sqrt { \langle v, v \rangle } $.</span><span class="sxs-lookup"><span data-stu-id="3351b-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="3351b-121">È possibile moltiplicare un vettore con un numero $c $ per formare un nuovo vettore le cui voci vengono moltiplicate per $c $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="3351b-122">È anche possibile aggiungere due vettori $u $ e $v $ per formare un nuovo vettore le cui voci sono la somma delle voci di $u $ e $v $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="3351b-123">Queste operazioni sono illustrate di seguito:</span><span class="sxs-lookup"><span data-stu-id="3351b-123">These operations are depicted below:</span></span>

<span data-ttu-id="3351b-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="3351b-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-125">u_1\\\\</span></span>
<span data-ttu-id="3351b-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-126">u_2\\\\</span></span>
<span data-ttu-id="3351b-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-127">\vdots\\\\</span></span>
<span data-ttu-id="3351b-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="3351b-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-129">v_1\\\\</span></span>
    <span data-ttu-id="3351b-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-130">v_2\\\\</span></span>
    <span data-ttu-id="3351b-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-131">\vdots\\\\</span></span>
    <span data-ttu-id="3351b-132">v_n \end{ bmatrix } , ~ \mathrm{Then } ~ au + BV = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="3351b-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="3351b-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="3351b-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-135">\vdots\\\\</span></span>
<span data-ttu-id="3351b-136">au_n + bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="3351b-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="3351b-137">Una [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) di dimensioni $m \times n $ è una raccolta di $MN $ numeri complessi disposti in $m $ righe e $n $ colonne, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3351b-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="3351b-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="3351b-139">M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="3351b-140">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {MN } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="3351b-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="3351b-141">Si noti che un vettore di $n dimensione $ è semplicemente una matrice di dimensioni $n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="3351b-142">Analogamente ai vettori, possiamo moltiplicare una matrice con un numero $c $ per ottenere una nuova matrice in cui ogni voce viene moltiplicata con $c $ ed è possibile aggiungere due matrici con le stesse dimensioni per produrre una nuova matrice le cui voci sono la somma delle rispettive voci delle due matrici.</span><span class="sxs-lookup"><span data-stu-id="3351b-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="3351b-143">Moltiplicazione di matrici e prodotti tensori</span><span class="sxs-lookup"><span data-stu-id="3351b-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="3351b-144">È anche possibile moltiplicare due matrici $M $ della dimensione $m \times n $ e $N $ della dimensione $n \times p $ per ottenere una nuova matrice $P $ della dimensione $m \times p $ , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3351b-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="3351b-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="3351b-145">\begin{align}</span></span>
<span data-ttu-id="3351b-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="3351b-147">M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="3351b-148">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {MN}</span><span class="sxs-lookup"><span data-stu-id="3351b-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="3351b-149">finebmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-149">\end{bmatrix}</span></span>
<span data-ttu-id="3351b-150">iniziarebmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-150">\begin{bmatrix}</span></span>
<span data-ttu-id="3351b-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1P } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2P } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="3351b-152">N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cdots ~ ~ N_ {NP}</span><span class="sxs-lookup"><span data-stu-id="3351b-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="3351b-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="3351b-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1P } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2P } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="3351b-155">P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {MP}</span><span class="sxs-lookup"><span data-stu-id="3351b-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="3351b-156">finebmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-156">\end{bmatrix}</span></span>
<span data-ttu-id="3351b-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="3351b-157">\end{align}</span></span>

<span data-ttu-id="3351b-158">dove le voci di $P $ sono $P _ {ik } = \ sum_j m_ {ij} N_ {JK } $.</span><span class="sxs-lookup"><span data-stu-id="3351b-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="3351b-159">La voce $P _ {11 $, ad esempio, } è il prodotto interno della prima riga di $M $ con la prima colonna di $N $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="3351b-160">Si noti che poiché un vettore è semplicemente un caso speciale di una matrice, questa definizione si estende alla moltiplicazione dei vettori di matrici.</span><span class="sxs-lookup"><span data-stu-id="3351b-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="3351b-161">Tutte le matrici considerate saranno matrici quadre, in cui il numero di righe e colonne è uguale, o vettori, che corrisponde solo a $1 $ colonna.</span><span class="sxs-lookup"><span data-stu-id="3351b-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="3351b-162">Una matrice quadrata speciale è la [*matrice di identità*](https://en.wikipedia.org/wiki/Identity_matrix), denotata $ \boldone $ , che include tutti gli elementi diagonali uguali a $1 $ e gli elementi rimanenti uguali a $0 $ :</span><span class="sxs-lookup"><span data-stu-id="3351b-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="3351b-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="3351b-164">1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="3351b-165">0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="3351b-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="3351b-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="3351b-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="3351b-168">Per una matrice quadrata $A $ viene indicato che una matrice $B $ è la relativa [*inversa*](https://en.wikipedia.org/wiki/Invertible_matrix) se $AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="3351b-169">L'inverso di una matrice non deve esistere, ma quando esiste è univoco e viene indicato $A ^ {-1 } $.</span><span class="sxs-lookup"><span data-stu-id="3351b-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="3351b-170">Per qualsiasi $M di matrice, la trasportazione $ contigua o coniugata di $M $ è una matrice $N $ tale che $N _ {IJ } = m_ {Ji } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="3351b-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="3351b-171">Il $M contiguo $ è in genere indicato $M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="3351b-172">Si dice che un $U matrice $ è [*unitario*](https://en.wikipedia.org/wiki/Unitary_matrix) se $UU ^ \dagger = U ^ \dagger U = \boldone $ o equivalente, $U ^ {-1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="3351b-173">Probabilmente la proprietà più importante delle matrici unitarie è che conservano la norma di un vettore.</span><span class="sxs-lookup"><span data-stu-id="3351b-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="3351b-174">Questo problema si verifica perché</span><span class="sxs-lookup"><span data-stu-id="3351b-174">This happens because</span></span> 

<span data-ttu-id="3351b-175">$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger u v = \Langle u v, u v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="3351b-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="3351b-176">Un $M matrice $ viene definito [*hermitiane*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $M = M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="3351b-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="3351b-177">Infine, il [*prodotto tensore*](https://en.wikipedia.org/wiki/Tensor_product) (o prodotto Kronecker) di due matrici $M $ di dimensioni $m \times n $ e $N $ di dimensioni $p \times q $ è una matrice di dimensioni maggiori $P = M \otimes n $ di dimensione $MP \times NQ $ e viene ottenuta da $M $ e $N $ come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3351b-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="3351b-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="3351b-178">\begin{align}</span></span>
    <span data-ttu-id="3351b-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="3351b-180">M_ {11 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="3351b-181">M_ {M1 } ~ ~ \cdots ~ ~ m_ {MN}</span><span class="sxs-lookup"><span data-stu-id="3351b-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="3351b-182">finebmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-182">\end{bmatrix}</span></span>
    <span data-ttu-id="3351b-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="3351b-184">N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="3351b-185">N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ}</span><span class="sxs-lookup"><span data-stu-id="3351b-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="3351b-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="3351b-187">M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {1N } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ } \end{ bmatrix } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3351b-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="3351b-188">M_ {M1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {MN } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1Q } \\ \\ \ddots \\\\ N_ {P1 } ~ ~ \cdots ~ ~ N_ {PQ } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="3351b-189">\end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="3351b-189">\end{bmatrix}.</span></span>
<span data-ttu-id="3351b-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="3351b-190">\end{align}</span></span>

<span data-ttu-id="3351b-191">Si tratta di una dimostrazione migliore con alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="3351b-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="3351b-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="3351b-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="3351b-194">\begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="3351b-195">\\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="3351b-196">finebmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-196">\end{bmatrix}</span></span>
    <span data-ttu-id="3351b-197">= \begin{ bmatrix } a c \\ \\ a d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\ \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="3351b-198">e</span><span class="sxs-lookup"><span data-stu-id="3351b-198">and</span></span>

<span data-ttu-id="3351b-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="3351b-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="3351b-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="3351b-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="3351b-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="3351b-204">\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="3351b-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="3351b-206">b \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="3351b-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="3351b-208">\\\\[1em] c \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="3351b-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="3351b-210">d \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="3351b-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="3351b-212">finebmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-212">\end{bmatrix}</span></span>
    <span data-ttu-id="3351b-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3351b-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="3351b-214">AE \ = \ è \ BF \\ \\ AG \ Ah \ BG \ BH \\ \\ CE \ CF \ de \ DF \\ \\ CG \ ch \ DG \ DH \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="3351b-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="3351b-215">Una convenzione di notazione utile finale che circonda i prodotti tensori è che, per qualsiasi $v vettoriale $ o matrice $M $ , $v ^ {\otimes n } $ o $M ^ {\otimes n } $ è una mano breve per un $ prodotto tensore ripetuto $n.</span><span class="sxs-lookup"><span data-stu-id="3351b-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="3351b-216">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3351b-216">For example:</span></span>

<span data-ttu-id="3351b-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="3351b-217">\begin{align}</span></span>
<span data-ttu-id="3351b-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 0 \\ \\ \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 &0&1&0 \\ \\ 0 &1&0&0 \\\\ 1 &0&0&0 \end { bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="3351b-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="3351b-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="3351b-219">\end{align}</span></span>
