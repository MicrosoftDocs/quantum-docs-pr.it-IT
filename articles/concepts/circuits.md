---
title: Circuiti quantistici
description: Informazioni su come rappresentare visivamente operazioni Quantum semplici e complesse con i diagrammi dei circuiti quantistici.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 80d9df00159090768ea442e519c34043a99b050c
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022650"
---
# <a name="quantum-circuits"></a><span data-ttu-id="e627b-103">Circuiti Quantum</span><span class="sxs-lookup"><span data-stu-id="e627b-103">Quantum Circuits</span></span>
<span data-ttu-id="e627b-104">Prendere in considerazione per un attimo la trasformazione unitaria $ \Text{CNOT} _{01}(H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="e627b-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="e627b-105">Questa sequenza di controllo è di importanza fondamentale per l'elaborazione quantistica, perché crea uno stato qubit con un massimo di due:</span><span class="sxs-lookup"><span data-stu-id="e627b-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="e627b-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="e627b-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="e627b-107">Le operazioni con questa o maggiore complessità sono onnipresenti negli algoritmi quantistici e nella correzione degli errori quantistici, quindi dovrebbe essere molto importante ottenere un metodo semplice per la visualizzazione denominata *diagramma del circuito quantistico*.</span><span class="sxs-lookup"><span data-stu-id="e627b-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="e627b-108">Il diagramma di circuito per la preparazione di questo stato quantico con la massima correlazione è:</span><span class="sxs-lookup"><span data-stu-id="e627b-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="e627b-109">diagramma di circuito di ![per uno stato di due qubit con un massimo di due](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="e627b-110">Convenzioni del diagramma del circuito quantistico</span><span class="sxs-lookup"><span data-stu-id="e627b-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="e627b-111">Questo linguaggio visivo per le operazioni quantum può essere più facilmente digeribile rispetto alla scrittura della matrice equivalente dopo aver compreso le convenzioni per esprimere un circuito Quantum.</span><span class="sxs-lookup"><span data-stu-id="e627b-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="e627b-112">Queste convenzioni sono riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="e627b-112">We review these conventions below.</span></span>

<span data-ttu-id="e627b-113">In un diagramma di circuito ogni linea continua raffigura un qubit o più in generale un registro qubit.</span><span class="sxs-lookup"><span data-stu-id="e627b-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="e627b-114">Per convenzione, la riga superiore è qubit register $0 $ e il resto è contrassegnato in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="e627b-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="e627b-115">Il circuito di esempio precedente viene illustrato come agendo su due qubits (o due registri equivalenti costituiti da un qubit).</span><span class="sxs-lookup"><span data-stu-id="e627b-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="e627b-116">Le attività di controllo che agiscono su uno o più registri qubit sono denotate come box.</span><span class="sxs-lookup"><span data-stu-id="e627b-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="e627b-117">Ad esempio, il simbolo</span><span class="sxs-lookup"><span data-stu-id="e627b-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="e627b-118">![simbolo per un'operazione Hadamard che agisce su un registro qubit singolo](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="e627b-119">è un'operazione [Hadamard](xref:microsoft.quantum.intrinsic.h) che agisce su un registro qubit singolo.</span><span class="sxs-lookup"><span data-stu-id="e627b-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="e627b-120">Le attività di controllo Quantum sono ordinate in ordine cronologico con il Gate più a sinistra quando il Gate viene applicato per primo a qubits.</span><span class="sxs-lookup"><span data-stu-id="e627b-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="e627b-121">In altre parole, se si immaginano i cavi con lo stato quantum, i fili portano lo stato del quantum attraverso ogni controllo nel diagramma da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="e627b-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="e627b-122">Ovvero</span><span class="sxs-lookup"><span data-stu-id="e627b-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="e627b-123">![diagramma di cancelli quantistici applicato da sinistra a destra](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-123">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="e627b-124">matrice unitaria $CBA $.</span><span class="sxs-lookup"><span data-stu-id="e627b-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="e627b-125">La moltiplicazione di matrici rispetta la convenzione opposta: viene applicata per prima la matrice più a destra.</span><span class="sxs-lookup"><span data-stu-id="e627b-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="e627b-126">Nei diagrammi del circuito quantistico, tuttavia, viene applicato per primo il Gate più a sinistra.</span><span class="sxs-lookup"><span data-stu-id="e627b-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="e627b-127">Questa differenza può talvolta comportare confusione, quindi è importante notare questa differenza significativa tra la notazione algebrica lineare e i diagrammi del circuito quantistico.</span><span class="sxs-lookup"><span data-stu-id="e627b-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="e627b-128">Input e output dei circuiti Quantum</span><span class="sxs-lookup"><span data-stu-id="e627b-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="e627b-129">Tutti gli esempi precedenti forniti hanno avuto esattamente lo stesso numero di fili (qubits) di input in un controllo Quantum come il numero di fili fuori dal controllo Quantum.</span><span class="sxs-lookup"><span data-stu-id="e627b-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="e627b-130">Potrebbe sembrare ragionevole che i circuiti Quantum possano avere più o meno output degli input in generale.</span><span class="sxs-lookup"><span data-stu-id="e627b-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="e627b-131">Questo non è possibile, tuttavia, perché tutte le operazioni Quantum, il salvataggio della misura, sono unitarie e pertanto reversibili.</span><span class="sxs-lookup"><span data-stu-id="e627b-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="e627b-132">Se non hanno lo stesso numero di output degli input, non sarebbero reversibili e, di conseguenza, non si trattasse di una contraddizione.</span><span class="sxs-lookup"><span data-stu-id="e627b-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="e627b-133">Per questo motivo, qualsiasi casella disegnata in un diagramma di circuito deve avere esattamente lo stesso numero di fili che li immette come uscita.</span><span class="sxs-lookup"><span data-stu-id="e627b-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="e627b-134">I diagrammi di circuito multiqubit seguono convenzioni simili a quelle a qubit singolo.</span><span class="sxs-lookup"><span data-stu-id="e627b-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="e627b-135">Come esempio chiarificante, è possibile definire un'operazione unitaria a due qubit $B $ come $ (H S\otimes X) $ ed esprimere il circuito in modo equivalente come</span><span class="sxs-lookup"><span data-stu-id="e627b-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="e627b-136">diagramma di circuito ![di un'operazione unitaria a due qubit](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-136">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="e627b-137">È anche possibile visualizzare $B $ come avente un'azione su un singolo registro qubit anziché 2 1 qubit a seconda del contesto in cui viene usato il circuito.</span><span class="sxs-lookup"><span data-stu-id="e627b-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="e627b-138">Probabilmente la proprietà più utile di questi diagrammi di circuito astratti è che consentono di descrivere algoritmi quantistici complessi a un livello elevato senza doverli compilare fino a controlli fondamentali.</span><span class="sxs-lookup"><span data-stu-id="e627b-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="e627b-139">Ciò significa che è possibile ottenere un'intuizione sul flusso di dati per un algoritmo Quantum di grandi dimensioni senza che sia necessario comprendere tutti i dettagli sul funzionamento di ciascuna subroutine all'interno dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="e627b-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="e627b-140">Controlli di controllo</span><span class="sxs-lookup"><span data-stu-id="e627b-140">Controlled gates</span></span>
<span data-ttu-id="e627b-141">L'altro costrutto incorporato nei diagrammi di circuito Quantum multiqubit è il controllo.</span><span class="sxs-lookup"><span data-stu-id="e627b-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="e627b-142">L'azione di un controllo Quantum controllato singolarmente, indicato $ \Lambda (G) $, in cui il valore di un singolo qubit controlla l'applicazione di $G $, può essere compreso osservando l'esempio seguente di un input di stato del prodotto $ \Lambda (G) (\Alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \Alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.</span><span class="sxs-lookup"><span data-stu-id="e627b-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="e627b-143">Ovvero, il controllo controllato si applica $G $ al registro contenente $ \psi $ se e solo se il qubit del controllo accetta il valore $1 $.</span><span class="sxs-lookup"><span data-stu-id="e627b-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="e627b-144">In generale, le operazioni controllate nei diagrammi di circuito sono descritte come</span><span class="sxs-lookup"><span data-stu-id="e627b-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="e627b-145">diagramma di circuito ![di un controllo che viene controllato singolarmente](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-145">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="e627b-146">Qui il cerchio nero indica il bit del quantum su cui è controllato il controllo e un cavo verticale indica l'elemento unitario applicato quando il qubit del controllo accetta il valore $1 $.</span><span class="sxs-lookup"><span data-stu-id="e627b-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="e627b-147">Per i casi speciali in cui $G = X $ e $G = Z $ introduciamo la notazione seguente per descrivere la versione controllata delle attività di controllo (si noti che il controllo X controllato è il [$CNOT $ Gate](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="e627b-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="e627b-148">diagramma di circuito ![per casi speciali di controlli di controllo](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-148">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="e627b-149">Q # fornisce metodi per generare automaticamente la versione controllata di un'operazione, che consente di salvare il programmatore dalla necessità di scrivere codice per queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="e627b-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="e627b-150">Un esempio è illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e627b-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="e627b-151">Operatore di misurazione</span><span class="sxs-lookup"><span data-stu-id="e627b-151">Measurement operator</span></span>
<span data-ttu-id="e627b-152">L'operazione rimanente da visualizzare nei diagrammi di circuito è la misurazione.</span><span class="sxs-lookup"><span data-stu-id="e627b-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="e627b-153">La misurazione accetta un registro qubit, lo misura e restituisce il risultato come informazioni classiche.</span><span class="sxs-lookup"><span data-stu-id="e627b-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="e627b-154">Un'operazione di misurazione è indicata da un simbolo del contatore e accetta sempre come input un registro qubit (indicato da una linea continua) e restituisce informazioni classiche (indicate da una doppia riga).</span><span class="sxs-lookup"><span data-stu-id="e627b-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="e627b-155">In particolare, questo sottocircuito ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e627b-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="e627b-156">![simbolo che rappresenta un'operazione di misurazione](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-156">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="e627b-157">Q # implementa un [operatore di misura](xref:microsoft.quantum.intrinsic.measure) a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="e627b-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="e627b-158">Per ulteriori informazioni, vedere la [sezione sulle misurazioni](xref:microsoft.quantum.libraries.standard.prelude#measurements) .</span><span class="sxs-lookup"><span data-stu-id="e627b-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="e627b-159">Analogamente, il sottocircuito</span><span class="sxs-lookup"><span data-stu-id="e627b-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="e627b-160">![diagramma di circuito che rappresenta un'operazione controllata](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-160">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="e627b-161">fornisce un controllo classico, in cui $G $ viene applicato condizionato al bit del controllo classico valore $1 $.</span><span class="sxs-lookup"><span data-stu-id="e627b-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="e627b-162">Diagramma del circuito di Teleportation</span><span class="sxs-lookup"><span data-stu-id="e627b-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="e627b-163">La [teleportazione quantistica](xref:microsoft.quantum.techniques.puttingittogether) è probabilmente l'algoritmo Quantum migliore per illustrare questi componenti.</span><span class="sxs-lookup"><span data-stu-id="e627b-163">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="e627b-164">La telemetria quantistica è un metodo per lo scorrimento dei dati all'interno di un computer quantistico (o anche tra computer Quantum lontani in una rete quantistica) tramite l'uso di un nodo e una misurazione.</span><span class="sxs-lookup"><span data-stu-id="e627b-164">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="e627b-165">È interessante notare che è effettivamente in grado di trasferire uno stato quantico, ad indicare il valore in un determinato qubit, da un qubit a un altro, senza nemmeno conoscere il valore di qubit.</span><span class="sxs-lookup"><span data-stu-id="e627b-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="e627b-166">Questa operazione è necessaria affinché il protocollo funzioni in base alle leggi di Quantum Mechanics.</span><span class="sxs-lookup"><span data-stu-id="e627b-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="e627b-167">Il circuito di Teleportation Quantum è riportato di seguito. viene anche fornita una versione con annotazioni del circuito per illustrare come leggere il circuito Quantum.</span><span class="sxs-lookup"><span data-stu-id="e627b-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="e627b-168">![circuito di teleportabilità Quantum](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="e627b-168">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
