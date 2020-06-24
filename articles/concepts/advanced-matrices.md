---
title: Concetti avanzati relativi alle matrici
description: Informazioni su autovettori, autovalori e matrici esponenziali, gli strumenti fondamentali usati per descrivere e simulare gli algoritmi Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- $$
- $$
- $$
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 71923247121eae6a1d4e26d2664d8e547370ba3a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269457"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="820ce-103">Concetti avanzati della matrice</span><span class="sxs-lookup"><span data-stu-id="820ce-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="820ce-104">Si estenderà ora la manipolazione delle matrici agli [*autovalori, autovettori*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ed [*esponenziali*](https://en.wikipedia.org/wiki/Matrix_exponential) , che costituiscono un insieme fondamentale di strumenti necessari per descrivere e implementare gli algoritmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="820ce-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="820ce-105">Autovalori e autovettori</span><span class="sxs-lookup"><span data-stu-id="820ce-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="820ce-106">$M $ essere una matrice quadrata e $v $ essere un vettore che non è il vettore di tutti gli zeri, ovvero il vettore con tutte le voci uguali a $0 $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="820ce-107">Si dice $v $ è un [*autovettore*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) di $M $ se $MV = CV $ per un certo numero $c $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="820ce-108">Si dice $c $ è [*autovalore*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corrispondente al $v autovettore $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="820ce-109">In generale, una matrice $M $ può trasformare un vettore in qualsiasi altro vettore, ma un autovettore è speciale perché viene lasciato invariato, ad eccezione del fatto che viene moltiplicato per un numero.</span><span class="sxs-lookup"><span data-stu-id="820ce-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="820ce-110">Si noti che se $v $ è un autovettore con $c autovalore $ , $AV $ è anche un autovettore (per qualsiasi $a diverso da zero $ ) con lo stesso autovalore.</span><span class="sxs-lookup"><span data-stu-id="820ce-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="820ce-111">Per la matrice di identità, ad esempio, ogni $v vettoriale $ è un autovettore con autovalore $1 $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="820ce-112">Per un altro esempio, si consideri una [*matrice diagonale*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ che ha solo voci non zero sulla diagonale:</span><span class="sxs-lookup"><span data-stu-id="820ce-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="820ce-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="820ce-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="820ce-114">d_1 & 0 & 0 \\ \\ 0 & D_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="820ce-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="820ce-115">Vettori</span><span class="sxs-lookup"><span data-stu-id="820ce-115">The vectors</span></span>

<span data-ttu-id="820ce-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end{bmatrix} e \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="820ce-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="820ce-117">sono autovettori di questa matrice con autovalori $d _1 $ , $d _2 $ e $d _3 $ rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="820ce-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="820ce-118">Se $d _1 $ , $d _2 $ e $d _3 $ sono numeri distinti, questi vettori (e i relativi multipli) sono l'unico autovettori della matrice $D $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="820ce-119">In generale, per una matrice diagonale è facile leggere gli autovalori e autovettori.</span><span class="sxs-lookup"><span data-stu-id="820ce-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="820ce-120">Gli autovalori sono tutti i numeri visualizzati sulla diagonale e i rispettivi autovettori sono i vettori di unità con una voce uguale a $1 $ e le voci rimanenti pari a $0 $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="820ce-121">Si noti che nell'esempio precedente il autovettori di $D $ costituisce una base per i $ vettori tridimensionali $3.</span><span class="sxs-lookup"><span data-stu-id="820ce-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="820ce-122">Una base è costituita da un set di vettori in modo che qualsiasi vettore possa essere scritto come una combinazione lineare.</span><span class="sxs-lookup"><span data-stu-id="820ce-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="820ce-123">In modo più esplicito, $v _1 $ , $v _2 $ e $v _3 $ costituiscono una base se $ è possibile scrivere qualsiasi $v vettoriale come $v = A_1 V_1 + A_2 v_2 + A_3 v_3 $ per alcuni numeri $a _1 $ , $a _2 $ e $a _3 $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="820ce-124">Tenere presente che una matrice Hermitiane (detta anche self-adiacentt) è una matrice quadrata complessa uguale al proprio coniugato complesso, mentre una matrice unitaria è una matrice quadrata complessa il cui inverso è uguale al suo complesso coniugato.</span><span class="sxs-lookup"><span data-stu-id="820ce-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="820ce-125">Per le matrici Hermitiane e unitarie, che sono essenzialmente le uniche matrici rilevate nel quantum computing, è presente un risultato generale noto come [*teorema spettrale*](https://en.wikipedia.org/wiki/Spectral_theorem), che asserisce quanto segue: per qualsiasi matrice di Hermitiane o unity $M $ , esiste una $U unitaria in $ modo tale che $M = U ^ \dagger D u $ per alcune $D della matrice diagonale $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="820ce-126">Inoltre, le voci diagonali di $D $ saranno gli autovalori di $M $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="820ce-127">È già noto come calcolare gli autovalori e la autovettori di una matrice diagonale $D $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="820ce-128">Con questo teorema sappiamo che se $v $ è un autovettore di $D $ con $c autovalore $ , ad esempio $DV = CV $ , $U ^ \dagger v $ sarà un autovettore di $M $ con autovalore $c $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="820ce-129">Questo perché</span><span class="sxs-lookup"><span data-stu-id="820ce-129">This is because</span></span>

<span data-ttu-id="820ce-130">$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $</span><span class="sxs-lookup"><span data-stu-id="820ce-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="820ce-131">Esponenziali matrice</span><span class="sxs-lookup"><span data-stu-id="820ce-131">Matrix Exponentials</span></span>
<span data-ttu-id="820ce-132">Una [*matrice esponenziale*](https://en.wikipedia.org/wiki/Matrix_exponential) può anche essere definita esattamente Analogamente alla funzione esponenziale.</span><span class="sxs-lookup"><span data-stu-id="820ce-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="820ce-133">Il valore esponenziale della matrice di una matrice $A $ può essere espresso come</span><span class="sxs-lookup"><span data-stu-id="820ce-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="820ce-134">$ $ e ^ A = \boldone + a + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \cdots $ $</span><span class="sxs-lookup"><span data-stu-id="820ce-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="820ce-135">Questo è importante perché l'evoluzione del tempo di Quantum Mechanical è descritta da una matrice unitaria nel formato $e ^ {iB } $ per la matrice hermitiane $B $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="820ce-136">Per questo motivo, l'esecuzione esponenziale della matrice è una parte fondamentale dell'elaborazione quantistica e in quanto tale Q # offre routine intrinseche per la descrizione di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="820ce-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="820ce-137">Ci sono molti modi per calcolare una matrice esponenziale in un computer classico e, in generale, l'approssimazione di un esponenziale tale esponenziale è irta di rischi.</span><span class="sxs-lookup"><span data-stu-id="820ce-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="820ce-138">Vedere [*Cleve Moler e Charles Van Loan. "Diciannove modi dubbi per calcolare l'esponenziale di una matrice". SIAM Review 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) per ulteriori informazioni sui problemi correlati.</span><span class="sxs-lookup"><span data-stu-id="820ce-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="820ce-139">Il modo più semplice per comprendere come calcolare l'esponenziale di una matrice è tramite gli autovalori e autovettori di tale matrice.</span><span class="sxs-lookup"><span data-stu-id="820ce-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="820ce-140">In particolare, il teorema spettrale illustrato sopra dice che per ogni Hermitiane o matrice unitaria $A esiste $ una matrice unitaria $U $ e una matrice diagonale $D $ tale che $A = U ^ \dagger D u $ .  A causa delle proprietà di unitarietà, $A ^ 2 = U ^ \dagger D ^ 2 U $ e allo stesso modo per qualsiasi power $p $ $A ^ p = U ^ \dagger D ^ p U $ .  Se si sostituisce questa operazione nella definizione dell'operatore dell'operatore esponenziale, si ottiene:</span><span class="sxs-lookup"><span data-stu-id="820ce-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="820ce-141">$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2!} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (D_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (D_ {nn } ) \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="820ce-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="820ce-142">In altre parole, se si trasforma in eigenbasis della matrice $A $ quindi il calcolo della matrice esponenziale è equivalente al calcolo dell'esponenziale comune degli autovalori della matrice.</span><span class="sxs-lookup"><span data-stu-id="820ce-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="820ce-143">Poiché il numero di operazioni in quantum computing comporta l'esecuzione di esponenziali matrice, questo espediente di trasformazione nel eigenbasis di una matrice per semplificare l'esecuzione dell'operatore esponenziale viene visualizzato spesso ed è la base per molti algoritmi quantistici, ad esempio i metodi di simulazione Quantum di tipo Trotter-Suzuki descritti più avanti in questa guida.</span><span class="sxs-lookup"><span data-stu-id="820ce-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="820ce-144">Un'altra proprietà utile è se $B $ è sia unitario che hermitiane, ad esempio $B = b ^ {-1 } = B ^ \dagger $ quindi $B ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="820ce-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="820ce-145">Applicando questa regola all'espansione precedente della matrice esponenziale e raggruppando i termini $ \boldone $ e $B $ , è possibile vedere che per qualsiasi valore reale $x $ identità</span><span class="sxs-lookup"><span data-stu-id="820ce-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="820ce-146">$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $</span><span class="sxs-lookup"><span data-stu-id="820ce-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="820ce-147">tiene.</span><span class="sxs-lookup"><span data-stu-id="820ce-147">holds.</span></span> <span data-ttu-id="820ce-148">Questo espediente è particolarmente utile in quanto consente di ragionare sulle azioni esponenziali della matrice, anche se la dimensione di $B $ è esponenzialmente grande, nel caso speciale in cui $B sia $ unitario che Hermitiane.</span><span class="sxs-lookup"><span data-stu-id="820ce-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
