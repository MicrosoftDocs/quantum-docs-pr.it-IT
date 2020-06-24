---
title: Misurazioni di Pauli
description: Informazioni su come usare le operazioni di misurazione di Pauli a qubit singola e a più livelli.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
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
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269474"
---
# <a name="pauli-measurements"></a><span data-ttu-id="91940-103">Misurazioni di Pauli</span><span class="sxs-lookup"><span data-stu-id="91940-103">Pauli Measurements</span></span>

<span data-ttu-id="91940-104">Nelle discussioni precedenti sono state illustrate le misure di base computazionali.</span><span class="sxs-lookup"><span data-stu-id="91940-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="91940-105">In realtà, esistono altre misure comuni che si verificano in quantum computing che, dal punto di vista della notazione, sono utili per esprimere in termini di misurazioni di base computazionale.</span><span class="sxs-lookup"><span data-stu-id="91940-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="91940-106">Quando si lavora con Q #, il tipo più comune di misurazioni che verrà eseguito sarà probabilmente *misurazioni di Pauli*, che generalizzano le misurazioni di base computazionali per includere le misurazioni in altre basi e la parità tra qubits diversi.</span><span class="sxs-lookup"><span data-stu-id="91940-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="91940-107">In questi casi, è comune discutere la misurazione di un operatore Pauli, in generale un operatore come $X, Y, Z $ o $Z \otimes z, x \otimes x, x \otimes y $ e così via.</span><span class="sxs-lookup"><span data-stu-id="91940-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="91940-108">In Q #, gli operatori di qubit Pauli sono in genere rappresentati da matrici di tipo `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="91940-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="91940-109">Ad esempio, per rappresentare $X \otimes Z \otimes Y $ , è possibile usare la matrice `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="91940-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="91940-110">La discussione sulla misurazione in termini di operatori Pauli è particolarmente comune nel sottocampo della correzione degli errori quantistici.</span><span class="sxs-lookup"><span data-stu-id="91940-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="91940-111">In Q # si segue una convenzione simile. viene ora illustrata questa visualizzazione alternativa delle misurazioni.</span><span class="sxs-lookup"><span data-stu-id="91940-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="91940-112">Prima di approfondire i dettagli su come pensare a una misurazione di Pauli, è utile considerare la misurazione di un singolo qubit all'interno di un computer Quantum allo stato quantum.</span><span class="sxs-lookup"><span data-stu-id="91940-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="91940-113">Si supponga di avere uno $ stato del quantum $n-qubit, quindi la misurazione di un qubit immediatamente regola la metà delle possibilità di $2 ^ n $ che lo stato potrebbe essere in.</span><span class="sxs-lookup"><span data-stu-id="91940-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="91940-114">In altre parole, la misurazione proietta lo stato del quantum su uno dei due spazi.</span><span class="sxs-lookup"><span data-stu-id="91940-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="91940-115">Possiamo generalizzare il modo in cui pensiamo alla misurazione per riflettere questa intuizione.</span><span class="sxs-lookup"><span data-stu-id="91940-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="91940-116">Per identificare in modo conciso questi spazi, è necessario un linguaggio per descriverli.</span><span class="sxs-lookup"><span data-stu-id="91940-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="91940-117">Per descrivere i due sottospazi, è possibile specificarli tramite una matrice in cui sono presenti solo due autovalori univoci, presi dalla Convenzione come $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="91940-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="91940-118">Per un semplice esempio di descrizione di sottospazi in questo modo, prendere in considerazione $Z $ :</span><span class="sxs-lookup"><span data-stu-id="91940-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="91940-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="91940-119">$$ \begin{align}</span></span>
  <span data-ttu-id="91940-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="91940-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="91940-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="91940-121">\end{align}</span></span>
$$

<span data-ttu-id="91940-122">Leggendo gli elementi diagonali della matrice Pauli-$Z $ , è possibile osservare che $Z $ dispone di due autovettori, $ \ket{0 } $ e $ \ket{1 } $, con gli autovalori corrispondenti $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="91940-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="91940-123">Quindi, se misuriamo il qubit e otteniamo `Zero` (corrispondente allo stato $ \ket{0 } $), sappiamo che lo stato del qubit è un autostato $ + 1 $ dell' $ operatore $Z.</span><span class="sxs-lookup"><span data-stu-id="91940-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="91940-124">Analogamente, se si ottiene `One` , sappiamo che lo stato di qubit è un autostato $-1 $ di $Z $ .</span><span class="sxs-lookup"><span data-stu-id="91940-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="91940-125">Questo processo viene definito nel linguaggio delle misurazioni di Pauli come "misurazione di Pauli $Z $ " ed è interamente equivalente all'esecuzione di una misurazione di base computazionale.</span><span class="sxs-lookup"><span data-stu-id="91940-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="91940-126">Qualsiasi \times matrice $2 2 $ che rappresenta una trasformazione unitaria di $Z $ soddisfa anche questo criterio.</span><span class="sxs-lookup"><span data-stu-id="91940-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="91940-127">È anche possibile usare una matrice $A = U ^ \dagger Z U $ , in cui $U $ è qualsiasi altra matrice unitaria, per assegnare a una matrice che definisce i due risultati di una misurazione nel rispettivo $ \pm 1 $ autovettori.</span><span class="sxs-lookup"><span data-stu-id="91940-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="91940-128">La notazione delle misurazioni di Pauli fa riferimento a questa equivalenza unitaria identificando le misurazioni $X, Y, Z $ come misurazioni equivalenti che possono essere eseguite per ottenere informazioni da un qubit.</span><span class="sxs-lookup"><span data-stu-id="91940-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="91940-129">Queste misurazioni sono fornite di seguito per praticità.</span><span class="sxs-lookup"><span data-stu-id="91940-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="91940-130">Misurazione di Pauli</span><span class="sxs-lookup"><span data-stu-id="91940-130">Pauli Measurement</span></span>  |<span data-ttu-id="91940-131">Trasformazione unitaria</span><span class="sxs-lookup"><span data-stu-id="91940-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="91940-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="91940-132">$Z$</span></span>               | <span data-ttu-id="91940-133">$ \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-133">$\boldone$</span></span>             |
| <span data-ttu-id="91940-134">$X$</span><span class="sxs-lookup"><span data-stu-id="91940-134">$X$</span></span>               | <span data-ttu-id="91940-135">$H$</span><span class="sxs-lookup"><span data-stu-id="91940-135">$H$</span></span>                    |
| <span data-ttu-id="91940-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="91940-136">$Y$</span></span>               | <span data-ttu-id="91940-137">$HS ^ {\dagger}$</span><span class="sxs-lookup"><span data-stu-id="91940-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="91940-138">Ovvero, l'uso di questo linguaggio "Measure $Y $ " equivale all'applicazione $HS ^ \dagger $ e quindi alla misurazione della base di calcolo, in cui [`S`](xref:microsoft.quantum.intrinsic.s) è un'operazione Quantum intrinseca talvolta denominata "Phase Gate" e può essere simulata dalla matrice unitaria.</span><span class="sxs-lookup"><span data-stu-id="91940-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="91940-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="91940-139">$$ \begin{align}</span></span>
    <span data-ttu-id="91940-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="91940-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="91940-141">1 & 0 \\ \\ 0 & \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="91940-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="91940-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="91940-142">\end{align}</span></span>
$$

<span data-ttu-id="91940-143">È anche equivalente all'applicazione di $HS ^ \dagger $ al vettore di stato quantum e quindi alla misurazione $Z $ , in modo che l'operazione seguente sia equivalente a `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="91940-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

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

<span data-ttu-id="91940-144">Lo stato corretto viene quindi trovato trasformando di nuovo in base al calcolo, che equivale a applicare $SH $ al vettore di stato quantum. nel frammento di codice precedente, la trasformazione alla base di calcolo viene gestita automaticamente dall'utilizzo del `within … apply` blocco.</span><span class="sxs-lookup"><span data-stu-id="91940-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="91940-145">In Q #, diciamo il risultato---ovvero, le informazioni classiche estratte dall'interazione con lo stato---sono fornite da un `Result` valore $j \In \\ {\Texttt{zero } , \texttt{One } \\ } $ che indica se il risultato è in $ (-1) ^ j $ eigenspace dell'operatore Pauli misurato.</span><span class="sxs-lookup"><span data-stu-id="91940-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="91940-146">Misurazioni a più qubit</span><span class="sxs-lookup"><span data-stu-id="91940-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="91940-147">Le misurazioni degli operatori qubit di Pauli sono definite in modo analogo, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="91940-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="91940-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 \\\\ 0&0&0&1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="91940-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="91940-149">In questo modo, i prodotti tensore di due operatori Pauli-$Z $ formano una matrice costituita da due spazi costituiti dagli autovalori $ + 1 $ e $-1 $ .</span><span class="sxs-lookup"><span data-stu-id="91940-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="91940-150">Come nel caso di un singolo qubit, entrambe costituiscono un mezzo di spazio che significa che la metà dello spazio vettoriale accessibile appartiene al eigenspace $ + 1 $ e la metà rimanente al eigenspace $-1 $ .</span><span class="sxs-lookup"><span data-stu-id="91940-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="91940-151">In generale, è facile vedere dalla definizione del prodotto tensore che tutti i prodotti tensori degli operatori di Pauli-$Z $ e l'identità obbediscono anche a questo.</span><span class="sxs-lookup"><span data-stu-id="91940-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="91940-152">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="91940-152">For example,</span></span>

<span data-ttu-id="91940-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="91940-153">$$ \begin{align}</span></span>
    <span data-ttu-id="91940-154">Z \otimes \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="91940-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="91940-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="91940-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="91940-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="91940-156">\end{align}</span></span>
$$

<span data-ttu-id="91940-157">Come prima, eventuali trasformazioni unitarie di tali matrici descrivono anche due spazi vuoti etichettati con autovalori di $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="91940-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="91940-158">Ad esempio, $X \otimes X = h \otimes h (z \otimes z) h \otimes h $ dall'identità che $Z = HxH $ .</span><span class="sxs-lookup"><span data-stu-id="91940-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="91940-159">Analogamente al caso qubit, tutte le misurazioni di qubit Pauli possono essere scritte come $U ^ \dagger (Z \otimes \ID) U $ per $4 \times $ matrici unitarie $U $ .</span><span class="sxs-lookup"><span data-stu-id="91940-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="91940-160">Le trasformazioni vengono enumerate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="91940-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="91940-161">Nella tabella seguente viene usato $ \operatorname{SWAP } $ per indicare la matrice $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="91940-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="91940-162">\operatorname{SWAP } & = \left (\begin{Matrix}</span><span class="sxs-lookup"><span data-stu-id="91940-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="91940-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}</span><span class="sxs-lookup"><span data-stu-id="91940-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="91940-164">$ $ usato per simulare l'operazione intrinseca [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="91940-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="91940-165">Misurazione di Pauli</span><span class="sxs-lookup"><span data-stu-id="91940-165">Pauli Measurement</span></span>     |<span data-ttu-id="91940-166">Trasformazione unitaria</span><span class="sxs-lookup"><span data-stu-id="91940-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="91940-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="91940-168">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="91940-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="91940-170">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="91940-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="91940-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="91940-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="91940-174">$HS ^ \dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="91940-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="91940-175">$ \boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="91940-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="91940-176">$ \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="91940-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="91940-177">$ \boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="91940-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="91940-178">$ (H \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="91940-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="91940-179">$ \boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="91940-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="91940-180">$ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="91940-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="91940-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="91940-181">$Z\otimes Z$</span></span> | <span data-ttu-id="91940-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="91940-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="91940-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="91940-183">$X\otimes Z$</span></span> | <span data-ttu-id="91940-184">$ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="91940-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="91940-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="91940-185">$Y\otimes Z$</span></span> | <span data-ttu-id="91940-186">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="91940-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="91940-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="91940-187">$Z\otimes X$</span></span> | <span data-ttu-id="91940-188">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="91940-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="91940-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="91940-189">$X\otimes X$</span></span> | <span data-ttu-id="91940-190">$ \operatorname{CNOT } \_ {10 } (h \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="91940-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="91940-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="91940-191">$Y\otimes X$</span></span> | <span data-ttu-id="91940-192">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="91940-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="91940-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="91940-193">$Z\otimes Y$</span></span> | <span data-ttu-id="91940-194">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="91940-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="91940-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="91940-195">$X\otimes Y$</span></span> | <span data-ttu-id="91940-196">$ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="91940-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="91940-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="91940-197">$Y\otimes Y$</span></span> | <span data-ttu-id="91940-198">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="91940-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="91940-199">In questo caso, l' [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operazione viene visualizzata per il motivo seguente.</span><span class="sxs-lookup"><span data-stu-id="91940-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="91940-200">Ogni misura di Pauli che non include la matrice $ \boldone $ è equivalente a un elemento unitario a $Z \otimes Z $ con la motivazione precedente.</span><span class="sxs-lookup"><span data-stu-id="91940-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="91940-201">Gli autovalori di $Z \otimes Z $ dipendono solo dalla parità dei qubits che comprendono ogni vettore di base computazionale e le operazioni controllate-not servono per calcolare questa parità e archiviarla nel primo bit.</span><span class="sxs-lookup"><span data-stu-id="91940-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="91940-202">Quindi, una volta misurato il primo bit, è possibile recuperare l'identità dello spazio a metà risultante, equivalente alla misurazione dell'operatore Pauli.</span><span class="sxs-lookup"><span data-stu-id="91940-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="91940-203">Una nota aggiuntiva: Sebbene sia possibile tentare di presupporre che la misurazione di $Z \otimes Z $ corrisponda alla misurazione sequenziale $Z \otimes \mathbb{1 } $ e quindi a $ \mathbb{1 } \otimes Z $ , questo presupposto è false.</span><span class="sxs-lookup"><span data-stu-id="91940-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="91940-204">Il motivo è che la misura $Z \otimes Z $ proietta lo stato del quantum in una autostato $ + 1 $ o $-1 $ di questi operatori.</span><span class="sxs-lookup"><span data-stu-id="91940-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="91940-205">Misurando $Z \otimes \mathbb{1 } $, quindi $ \Mathbb{1 } \otimes z $ proietta il vettore di stato del Quantum prima in una metà dello spazio di $Z \otimes \mathbb{1 } $ e quindi su uno spazio metà di $ \mathbb{1 } \otimes z $ . Poiché sono presenti quattro vettori di base di calcolo, l'esecuzione di entrambe le misurazioni riduce lo stato a un trimestre e quindi lo riduce a un singolo vettore di base computazionale.</span><span class="sxs-lookup"><span data-stu-id="91940-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="91940-206">Correlazioni tra qubits</span><span class="sxs-lookup"><span data-stu-id="91940-206">Correlations between qubits</span></span>
<span data-ttu-id="91940-207">Un altro modo per esaminare i prodotti tensori di matrici di Pauli come $X \otimes X $ o $Z \otimes Z $ è che tali misure consentono di esaminare le informazioni archiviate nelle correlazioni tra le due qubits.</span><span class="sxs-lookup"><span data-stu-id="91940-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="91940-208">La misurazione $X \otimes \ID $ consente di esaminare le informazioni archiviate localmente nella prima qubit.</span><span class="sxs-lookup"><span data-stu-id="91940-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="91940-209">Sebbene entrambi i tipi di misurazioni siano ugualmente utili nell'elaborazione quantistica, il primo illumina la potenza del quantum computing.</span><span class="sxs-lookup"><span data-stu-id="91940-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="91940-210">Si rivela che in quantum computing, spesso le informazioni che si desidera apprendere non vengono archiviate in un singolo qubit, ma piuttosto archiviate in modo non locale in tutti i qubits in una sola volta e quindi esaminate solo tramite una misurazione congiunta, ad esempio $Z \otimes Z, $ le informazioni diventano manifeste.</span><span class="sxs-lookup"><span data-stu-id="91940-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="91940-211">Nella correzione degli errori, ad esempio, si desidera spesso conoscere l'errore che si è verificato durante l'apprendimento di nulla sullo stato che si sta tentando di proteggere.</span><span class="sxs-lookup"><span data-stu-id="91940-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="91940-212">Nell' [esempio di codice di tipo bit-flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) viene illustrato un esempio di come è possibile utilizzare misure come $Z \otimes Z \otimes \ID $ e $ \ID \Otimes z \otimes z $ .</span><span class="sxs-lookup"><span data-stu-id="91940-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="91940-213">È possibile misurare anche operatori Pauli arbitrari, ad esempio $X \otimes Y \Otimes Z \otimes \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="91940-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="91940-214">Tutti questi prodotti tensore di operatori Pauli hanno solo due autonomie $ \pm 1 $ e entrambi eigenspaces costituiscono metà spazi dell'intero spazio vettoriale.</span><span class="sxs-lookup"><span data-stu-id="91940-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="91940-215">Coincidono quindi con i requisiti indicati sopra.</span><span class="sxs-lookup"><span data-stu-id="91940-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="91940-216">In Q # tali misurazioni restituiscono $j $ se la misurazione restituisce un risultato in eigenspace del segno $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="91940-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="91940-217">Le misurazioni di Pauli come funzionalità incorporata in Q # sono utili perché la misurazione di tali operatori richiede lunghe catene di trasformazioni di base e non controllate per descrivere il diagonalizing $U $ Gate necessario per esprimere l'operazione come prodotto tensore di $Z $ e $ \ID $ . Con la possibilità di specificare che si desidera eseguire una di queste misurazioni predefinite, non è necessario preoccuparsi di come trasformare la base in modo che una misura di base computazionale fornisca le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="91940-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="91940-218">Q # gestisce automaticamente tutte le trasformazioni di base necessarie.</span><span class="sxs-lookup"><span data-stu-id="91940-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="91940-219">Per ulteriori informazioni, vedere le [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operazioni e.</span><span class="sxs-lookup"><span data-stu-id="91940-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="91940-220">Teorema di no-cloning</span><span class="sxs-lookup"><span data-stu-id="91940-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="91940-221">Le informazioni sul quantum sono potenti.</span><span class="sxs-lookup"><span data-stu-id="91940-221">Quantum information is powerful.</span></span>
<span data-ttu-id="91940-222">Ci permette di eseguire operazioni straordinarie, ad esempio numeri di fattore esponenzialmente più veloci rispetto agli algoritmi classici più noti, oppure simulare in modo efficiente i sistemi elettronici correlati che richiedono in genere un costo esponenziale per simulare in modo accurato.</span><span class="sxs-lookup"><span data-stu-id="91940-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="91940-223">Esistono tuttavia alcune limitazioni alla potenza del quantum computing.</span><span class="sxs-lookup"><span data-stu-id="91940-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="91940-224">Una limitazione di questo tipo viene fornita dal *teorema di no-cloning*.</span><span class="sxs-lookup"><span data-stu-id="91940-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="91940-225">Il teorema dell'assenza di clonazione è denominato.</span><span class="sxs-lookup"><span data-stu-id="91940-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="91940-226">Non consente la clonazione di stati Quantum generici da un computer Quantum.</span><span class="sxs-lookup"><span data-stu-id="91940-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="91940-227">La prova del teorema è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="91940-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="91940-228">Anche se una prova completa del teorema di non clonazione è un po' troppo tecnica per la nostra discussione, la prova, nel caso di nessun qubits ausiliario aggiuntivo, è all'interno dell'ambito (qubits ausiliari sono qubits usati per lo spazio scratch durante un calcolo e sono facilmente utilizzabili e gestiti in Q #, vedere la pagina relativa a [qubits in prestito](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="91940-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="91940-229">Per tale computer quantistico, l'operazione di clonazione deve essere descritta da una matrice unitaria.</span><span class="sxs-lookup"><span data-stu-id="91940-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="91940-230">Non è consentita la misurazione, perché danneggia lo stato del quantum che si sta tentando di clonare.</span><span class="sxs-lookup"><span data-stu-id="91940-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="91940-231">Per simulare l'operazione di clonazione, è necessario che la matrice unitaria venga utilizzata per la proprietà che $ $ U \ket { \psi } \ket{0 } = \ket { \psi \ket } { \psi}</span><span class="sxs-lookup"><span data-stu-id="91940-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="91940-232">$ $ per qualsiasi stato $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="91940-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="91940-233">La proprietà Linearity della moltiplicazione di matrici implica quindi che per qualsiasi secondo stato del quantum $ \ket { \Phi } $,</span><span class="sxs-lookup"><span data-stu-id="91940-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="91940-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="91940-234">$$ \begin{align}</span></span>
    <span data-ttu-id="91940-235">U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \Phi } + \ket { \psi } \right) \right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="91940-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="91940-236">& = \frac{1 } {\sqrt{2 } } U \ket { \Phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="91940-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="91940-237">+ \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \Phi } \ket { \Phi } + \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="91940-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="91940-238">\right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \Phi } + \ket \psi \right) \right) \otimes { } \left (\frac{1 } {\sqrt{2 } } \left (\ket { \Phi } + \ket { \psi \right } ) \right).</span><span class="sxs-lookup"><span data-stu-id="91940-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="91940-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="91940-239">\end{align}</span></span>
$$

<span data-ttu-id="91940-240">Si tratta di un'intuizione fondamentale dietro il teorema di no-cloning: qualsiasi dispositivo che copia uno stato quantum sconosciuto deve causare errori in almeno alcuni degli stati copiati.</span><span class="sxs-lookup"><span data-stu-id="91940-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="91940-241">Sebbene il presupposto fondamentale che il Cloner agisca in modo lineare sullo stato di input possa essere violato tramite l'aggiunta e la misurazione di qubits ausiliari, tali interazioni perdono anche le informazioni sul sistema attraverso le statistiche di misurazione e impediscono la clonazione esatta in tali casi.</span><span class="sxs-lookup"><span data-stu-id="91940-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="91940-242">Per una prova più completa del teorema di non clonazione, vedere [per altre informazioni](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="91940-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="91940-243">Il teorema di no-cloning è importante per la comprensione qualitativa del quantum computing, perché se è possibile clonare gli Stati Quantum a costo elevato, è possibile ottenere una capacità quasi magica di apprendere dagli Stati Quantum.</span><span class="sxs-lookup"><span data-stu-id="91940-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="91940-244">In realtà, è possibile violare il principio di incertezza decantato di Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="91940-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="91940-245">In alternativa, è possibile usare un Cloner ottimale per ottenere un singolo campione da una distribuzione quantistica complessa e apprendere tutti gli elementi che è possibile conoscere per la distribuzione da un solo esempio.</span><span class="sxs-lookup"><span data-stu-id="91940-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="91940-246">Si tratta di un'operazione analoga a quella di una moneta e di osservare le teste, quindi quando si comunica a un amico il risultato che li risponde "Ah la distribuzione di tale moneta deve essere di Bernoulli con $p = 0.512643 \ ldots $ !".</span><span class="sxs-lookup"><span data-stu-id="91940-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="91940-247">Un'istruzione di questo tipo non è sensical, perché una certa quantità di informazioni (il risultato delle intestazioni) non è semplicemente in grado di fornire le informazioni necessarie per codificare la distribuzione senza sostanziali informazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="91940-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="91940-248">In modo analogo, senza informazioni precedenti, non è possibile clonare perfettamente uno stato quantico proprio come non è possibile preparare un insieme di tali monete senza conoscere $p $ .</span><span class="sxs-lookup"><span data-stu-id="91940-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="91940-249">Le informazioni non sono gratuite in quantum computing.</span><span class="sxs-lookup"><span data-stu-id="91940-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="91940-250">Ogni qubit misurato fornisce un solo bit di informazioni e il teorema di no-cloning Mostra che non è presente alcuna backdoor che può essere sfruttata per aggirare il compromesso fondamentale tra le informazioni acquisite sul sistema e il disturbo richiamato al suo interno.</span><span class="sxs-lookup"><span data-stu-id="91940-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
