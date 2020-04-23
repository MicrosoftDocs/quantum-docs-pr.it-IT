---
title: Tecniche Q - Mettere tutto insieme
description: Passeggiata attraverso un programma di base di Q , che dimostra il teletrasporto quantistico.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030566"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="9512a-103">Mettere tutto insieme: teletrasporto</span><span class="sxs-lookup"><span data-stu-id="9512a-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="9512a-104">Torniamo all'esempio del circuito di teletrasporto definito in [Circuiti Quantici](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="9512a-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="9512a-105">Useremo questo per illustrare i concetti che abbiamo imparato finora.</span><span class="sxs-lookup"><span data-stu-id="9512a-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="9512a-106">Una spiegazione del teletrasporto quantistico è fornita di seguito per coloro che non hanno familiarità con la teoria, seguita da una procedura dettagliata dell'implementazione del codice in Q .</span><span class="sxs-lookup"><span data-stu-id="9512a-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="9512a-107">Teletrasporto quantico: Teoria</span><span class="sxs-lookup"><span data-stu-id="9512a-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="9512a-108">Il teletrasporto quantistico è una tecnica per l'invio di uno stato quantico sconosciuto (che ci riferiremo come il '__messaggio__') da un qubit in una posizione a un qubit in un'altra posizione (faremo riferimento a questi qubit come '__qui__' e '__lì__', rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="9512a-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="9512a-109">Possiamo rappresentare il nostro __messaggio__ come un vettore utilizzando la notazione Dirac:</span><span class="sxs-lookup"><span data-stu-id="9512a-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="9512a-110">"Ket" , "psi" , "alpha"{0} , "beta" e "", ""ket"{1}</span><span class="sxs-lookup"><span data-stu-id="9512a-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="9512a-111">Lo stato del __qubit__ del messaggio è sconosciuto a noi come non conosciamo i valori di "alpha" e "beta" .</span><span class="sxs-lookup"><span data-stu-id="9512a-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="9512a-112">Passaggio 1: Creare uno stato aggrovigliatoStep 1: Create an entangled state</span><span class="sxs-lookup"><span data-stu-id="9512a-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="9512a-113">Al fine di inviare il __messaggio__ abbiamo bisogno per il qubit __qui__ per essere impigliato con il qubit __lì__.</span><span class="sxs-lookup"><span data-stu-id="9512a-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="9512a-114">Ciò si ottiene applicando un cancello Hadamard, seguito da un cancello CNOT.</span><span class="sxs-lookup"><span data-stu-id="9512a-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="9512a-115">Diamo un'occhiata alla matematica dietro queste operazioni cancello.</span><span class="sxs-lookup"><span data-stu-id="9512a-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="9512a-116">Inizieremo con i qubit __qua__ e __là__ sia{0}nello stato di "ket".</span><span class="sxs-lookup"><span data-stu-id="9512a-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="9512a-117">Dopo aver impacchetto questi qubit, sono nello stato:</span><span class="sxs-lookup"><span data-stu-id="9512a-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="9512a-118">"Ket"{1}, "phi" e "ph",{2}{00} {11}"in ccomp".</span><span class="sxs-lookup"><span data-stu-id="9512a-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="9512a-119">Passaggio 2: Inviare il messaggio</span><span class="sxs-lookup"><span data-stu-id="9512a-119">Step 2: Send the message</span></span>
<span data-ttu-id="9512a-120">Per inviare il __messaggio,__ prima applichiamo un gate CNOT con il __qubit__ del messaggio e __qui__ qubit come input (il qubit del __messaggio__ è il controllo e il qubit __qui__ è il qubit di destinazione, in questo caso).</span><span class="sxs-lookup"><span data-stu-id="9512a-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="9512a-121">Questo stato di input può essere scritto:This input state can be written:</span><span class="sxs-lookup"><span data-stu-id="9512a-121">This input state can be written:</span></span>

<span data-ttu-id="9512a-122">- "ket" , "setro"{0} o "ket"{1}{1}{2}{00} {11}( )</span><span class="sxs-lookup"><span data-stu-id="9512a-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="9512a-123">Questo si espande a:</span><span class="sxs-lookup"><span data-stu-id="9512a-123">This expands to:</span></span>

<span data-ttu-id="9512a-124">"ket"{2}, "ket" , "setro" , "setro" , "phi"{000} {2}{011} {2}{100} {2}{111} , ".</span><span class="sxs-lookup"><span data-stu-id="9512a-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="9512a-125">Come promemoria, il cancello CNOT capovolge il qubit di destinazione quando il qubit di controllo è 1.</span><span class="sxs-lookup"><span data-stu-id="9512a-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="9512a-126">Quindi, ad esempio, un input{000}di , ovvero un valore di "ket", non comporterà alcuna modifica in quanto il primo qubit (il controllo) è 0.</span><span class="sxs-lookup"><span data-stu-id="9512a-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="9512a-127">Tuttavia, prendere un caso in cui il primo qubit è{100}1 - per esempio un input di .</span><span class="sxs-lookup"><span data-stu-id="9512a-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="9512a-128">In questo caso, l'output{110}è il file ,ket, poiché il secondo qubit (la destinazione) viene capovolto dal gate CNOT.</span><span class="sxs-lookup"><span data-stu-id="9512a-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="9512a-129">Consideriamo ora il nostro output una volta che il cancello CNOT ha agito sul nostro input sopra.</span><span class="sxs-lookup"><span data-stu-id="9512a-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="9512a-130">Il risultato è:</span><span class="sxs-lookup"><span data-stu-id="9512a-130">The result is:</span></span>

<span data-ttu-id="9512a-131">"frac" , alfa{2}, sqrt ,{000} sqrt , sqt{2}{011} {2}{101} , alpha , sqrt , ket{2}{110} , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , ,</span><span class="sxs-lookup"><span data-stu-id="9512a-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="9512a-132">Il passaggio successivo per inviare il __messaggio__ consiste nell'applicare una porta Hadamard al __qubit__ del messaggio (questo è il primo qubit di ogni termine).</span><span class="sxs-lookup"><span data-stu-id="9512a-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="9512a-133">Come promemoria, la porta Hadamard fa quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9512a-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="9512a-134">Input</span><span class="sxs-lookup"><span data-stu-id="9512a-134">Input</span></span> | <span data-ttu-id="9512a-135">Output</span><span class="sxs-lookup"><span data-stu-id="9512a-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="9512a-136">N. di{0}dollari per il tallustio.</span><span class="sxs-lookup"><span data-stu-id="9512a-136">$\ket{0}$</span></span>  | <span data-ttu-id="9512a-137">"frac"{1}(""terrore"{2}("ket"{0} {1})</span><span class="sxs-lookup"><span data-stu-id="9512a-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="9512a-138">N. di{1}dollari per il tallustio.</span><span class="sxs-lookup"><span data-stu-id="9512a-138">$\ket{1}$</span></span>  | <span data-ttu-id="9512a-139">(-tt){1}{2}{0} {1}</span><span class="sxs-lookup"><span data-stu-id="9512a-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="9512a-140">Se applichiamo la porta Hadamard al primo qubit di ogni termine del nostro output precedente, otteniamo il seguente risultato:</span><span class="sxs-lookup"><span data-stu-id="9512a-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="9512a-141">{2}Per il tipo di telefono, sqrt, si sqrt{1}{2}{0} {1}{00} {2}{1}{2}{0} {1}{11} ( . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .{2}. . .{1}. .{2}. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . ('''questo').{0} {1}{10} {2}{1}{2}{0} {1}{01}</span><span class="sxs-lookup"><span data-stu-id="9512a-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="9512a-142">Si noti che per ogni{1}termine sono{2}presenti due fattori di tipo .frac.</span><span class="sxs-lookup"><span data-stu-id="9512a-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="9512a-143">Possiamo moltiplicarli dando il seguente risultato:</span><span class="sxs-lookup"><span data-stu-id="9512a-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="9512a-144">"frac" ('ket'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''{2}{0} {1}{00} {2}{0} {1}{11} {2}{0} {1}{10} {2}{0} {1}{01}</span><span class="sxs-lookup"><span data-stu-id="9512a-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="9512a-145">Il fattore{1}{2}di frac è comune a ogni termine in modo che ora possiamo portarlo al di fuori delle parentesi quadre:</span><span class="sxs-lookup"><span data-stu-id="9512a-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="9512a-146">"frac"{1}{2}[-grande[ , alfa{0} ( ,{1}xket{00} ) , ket{0} , alfa ({1}{11} {0} {1}{10} {0} {1}{01}, , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , ,</span><span class="sxs-lookup"><span data-stu-id="9512a-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="9512a-147">Possiamo quindi moltiplicare le staffe per ogni termine dando:</span><span class="sxs-lookup"><span data-stu-id="9512a-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="9512a-148">{1}{2}"frac" ["grande" [ .{000} {100} {011} {111} {010} {110} {001} {101}. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .</span><span class="sxs-lookup"><span data-stu-id="9512a-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="9512a-149">Passaggio 3: Misurare il risultatoStep 3: Measure the result</span><span class="sxs-lookup"><span data-stu-id="9512a-149">Step 3: Measure the result</span></span>

<span data-ttu-id="9512a-150">A causa di __qua__ e __là__ essere impigliato, qualsiasi misura __qui__ influenzerà lo stato di __lì__.</span><span class="sxs-lookup"><span data-stu-id="9512a-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="9512a-151">Se misuriamo il primo e il secondo qubit (__messaggio__ e __qui__) possiamo imparare in quale stato __c'è,__ a causa di questa proprietà di impigliamento.</span><span class="sxs-lookup"><span data-stu-id="9512a-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="9512a-152">Se misuriamo e otteniamo un risultato 00, la sovrapposizione collassa, lasciando solo termini coerenti con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="9512a-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="9512a-153">Questo è il valore di{000} "alpha" o{001}"beta".</span><span class="sxs-lookup"><span data-stu-id="9512a-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="9512a-154">È possibile eseguire il refactoring{00}di questo file{0} nel percorso di{1}addizione in .</span><span class="sxs-lookup"><span data-stu-id="9512a-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="9512a-155">Pertanto, se si misura il primo e il secondo qubit a 00, sappiamo che il{0} terzo qubit,{1} __c'è__, è nello stato .</span><span class="sxs-lookup"><span data-stu-id="9512a-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="9512a-156">Se misuriamo e otteniamo un risultato 01, la sovrapposizione collassa, lasciando solo termini coerenti con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="9512a-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="9512a-157">Questo è il valore di{011} "alpha" o{010}"beta".</span><span class="sxs-lookup"><span data-stu-id="9512a-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="9512a-158">È possibile eseguire il refactoring{01}di questo file{1} nel percorso di{0}addizione in .</span><span class="sxs-lookup"><span data-stu-id="9512a-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="9512a-159">Pertanto, se si misura il primo e il secondo qubit per essere 01, sappiamo che il terzo qubit, __c'è__, è nello stato .{1} {0}</span><span class="sxs-lookup"><span data-stu-id="9512a-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="9512a-160">Se misuriamo e otteniamo un risultato 10, la sovrapposizione collassa, lasciando solo termini coerenti con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="9512a-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="9512a-161">Che è alfa-ket{100} - beta -ket{101}.</span><span class="sxs-lookup"><span data-stu-id="9512a-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="9512a-162">È possibile eseguire il refactoring{10}di questo file{0} a{1}.</span><span class="sxs-lookup"><span data-stu-id="9512a-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="9512a-163">Pertanto, se si misura il primo e il secondo qubit per essere 10, sappiamo che il terzo qubit, __c'è__, è nello stato .{0} {1}</span><span class="sxs-lookup"><span data-stu-id="9512a-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="9512a-164">Se misuriamo e otteniamo un risultato 11, la sovrapposizione collassa, lasciando solo termini coerenti con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="9512a-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="9512a-165">Che è alfa-ket{111} - beta -ket{110}.</span><span class="sxs-lookup"><span data-stu-id="9512a-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="9512a-166">È possibile eseguire il refactoring{11}di questo file{1} a{0}.</span><span class="sxs-lookup"><span data-stu-id="9512a-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="9512a-167">Pertanto, se si misura il primo e il secondo qubit per essere 11, sappiamo che il terzo qubit, __c'è__, è nello stato .{1} {0}</span><span class="sxs-lookup"><span data-stu-id="9512a-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="9512a-168">Passaggio 4: Interpretare il risultatoStep 4: Interpret the result</span><span class="sxs-lookup"><span data-stu-id="9512a-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="9512a-169">Come promemoria, il __messaggio__ originale che volevamo inviare era:</span><span class="sxs-lookup"><span data-stu-id="9512a-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="9512a-170">"Ket" , "psi" , "alpha"{0} , "beta" e "", ""ket"{1}</span><span class="sxs-lookup"><span data-stu-id="9512a-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="9512a-171">Abbiamo bisogno di ottenere il __qubit lì__ in questo stato, in modo che lo stato ricevuto è quello che è stato destinato.</span><span class="sxs-lookup"><span data-stu-id="9512a-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="9512a-172">Se abbiamo misurato e ottenuto un risultato di 00, quindi il terzo qubit, __c'è__, è nello stato .{0} {1}</span><span class="sxs-lookup"><span data-stu-id="9512a-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="9512a-173">Poiché questo è il __messaggio__previsto, non è necessaria alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="9512a-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="9512a-174">Se abbiamo misurato e ottenuto un risultato di 01, quindi il terzo qubit, __c'è__, è nello stato .{1} {0}</span><span class="sxs-lookup"><span data-stu-id="9512a-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="9512a-175">Questo è diverso dal __messaggio__previsto , tuttavia l'applicazione di un gate{0} NOT ci dà{1}lo stato desiderato .</span><span class="sxs-lookup"><span data-stu-id="9512a-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="9512a-176">Se abbiamo misurato e ottenuto un risultato di 10, quindi il terzo qubit, __c'è__, è nello stato .{0} {1}</span><span class="sxs-lookup"><span data-stu-id="9512a-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="9512a-177">Questo è diverso dal __messaggio__desiderato , tuttavia l'applicazione di un gate{0} di z ci{1}dà lo stato desiderato .</span><span class="sxs-lookup"><span data-stu-id="9512a-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="9512a-178">Se abbiamo misurato e ottenuto un risultato di 11, quindi il terzo qubit, __c'è__, è nello stato .{1} {0}</span><span class="sxs-lookup"><span data-stu-id="9512a-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="9512a-179">Questo è diverso dal __messaggio__previsto , tuttavia l'applicazione di un gate NOT seguito{0} da un gate{1}di z ci dà lo stato desiderato .</span><span class="sxs-lookup"><span data-stu-id="9512a-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="9512a-180">Per riassumere, se misuriamo e il primo qubit è 1, viene applicato un gate .</span><span class="sxs-lookup"><span data-stu-id="9512a-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="9512a-181">Se misuriamo e il secondo qubit è 1, viene applicato un cancello NON.</span><span class="sxs-lookup"><span data-stu-id="9512a-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="9512a-182">Summary</span><span class="sxs-lookup"><span data-stu-id="9512a-182">Summary</span></span>
<span data-ttu-id="9512a-183">Di seguito è mostrato un circuito quantistico di libri di testo che implementa il teletrasporto.</span><span class="sxs-lookup"><span data-stu-id="9512a-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="9512a-184">Spostandosi da sinistra a destra si può vedere:</span><span class="sxs-lookup"><span data-stu-id="9512a-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="9512a-185">Passo 1: Entangling __qua__ e __là__ applicando un cancello Hadamard e un cancello CNOT.</span><span class="sxs-lookup"><span data-stu-id="9512a-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="9512a-186">Passo 2: Invio del __messaggio__ utilizzando un cancello CNOT e un cancello Hadamard.</span><span class="sxs-lookup"><span data-stu-id="9512a-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="9512a-187">Passo 3: Prendendo una misura del primo e secondo qubit, __messaggio__ e __qui__.</span><span class="sxs-lookup"><span data-stu-id="9512a-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="9512a-188">Passo 4: Applicare un cancello NOT o un cancello , a seconda del risultato della misurazione nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="9512a-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!['Teleport(msg: Qubit, ci: Qubit) : Unità'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="9512a-190">Teletrasporto quantico: Codice</span><span class="sxs-lookup"><span data-stu-id="9512a-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="9512a-191">Abbiamo il nostro circuito per il teletrasporto quantistico:</span><span class="sxs-lookup"><span data-stu-id="9512a-191">We have our circuit for quantum teleportation:</span></span>

!['Teleport(msg: Qubit, ci: Qubit) : Unità'](~/media/teleportation.svg)

<span data-ttu-id="9512a-193">Ora possiamo tradurre ciascuno dei passaggi di questo circuito quantistico in Q.</span><span class="sxs-lookup"><span data-stu-id="9512a-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="9512a-194">Fase 0: Definizione</span><span class="sxs-lookup"><span data-stu-id="9512a-194">Step 0: Definition</span></span>
<span data-ttu-id="9512a-195">Quando eseguiamo il teletrasporto, dobbiamo conoscere il __messaggio__ che vogliamo inviare, e dove vogliamo inviarlo __(lì__).</span><span class="sxs-lookup"><span data-stu-id="9512a-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="9512a-196">Per questo motivo, iniziamo definendo una nuova operazione di teletrasporto che viene dato due qubit come argomenti, `msg` e `there`:</span><span class="sxs-lookup"><span data-stu-id="9512a-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="9512a-197">Abbiamo anche bisogno di `here` allocare un `using` qubit che otteniamo con un blocco:</span><span class="sxs-lookup"><span data-stu-id="9512a-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="9512a-198">Passaggio 1: Creare uno stato aggrovigliatoStep 1: Create an entangled state</span><span class="sxs-lookup"><span data-stu-id="9512a-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="9512a-199">Possiamo quindi creare la coppia `here` impigliata tra e `there` utilizzando le @"microsoft.quantum.intrinsic.h" operazioni e @"microsoft.quantum.intrinsic.cnot" :</span><span class="sxs-lookup"><span data-stu-id="9512a-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="9512a-200">Passaggio 2: Inviare il messaggio</span><span class="sxs-lookup"><span data-stu-id="9512a-200">Step 2: Send the message</span></span>
<span data-ttu-id="9512a-201">Per spostare il qubit del messaggio, viene quindi utilizzato i successivi gate di $H tipo nomeoperatore E CNOT:</span><span class="sxs-lookup"><span data-stu-id="9512a-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="9512a-202">Fase 3 & 4: Misurare e interpretare il risultato</span><span class="sxs-lookup"><span data-stu-id="9512a-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="9512a-203">Infine, utilizziamo @"microsoft.quantum.intrinsic.m" per eseguire le misurazioni ed eseguire le operazioni di `if` gate necessarie per ottenere lo stato desiderato, come indicato da istruzioni:</span><span class="sxs-lookup"><span data-stu-id="9512a-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="9512a-204">Passaggio 5: Riavviare il registro qubitStep 5: Restarting the qubit register</span><span class="sxs-lookup"><span data-stu-id="9512a-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="9512a-205">Alla fine di ogni operazione di Q, è necessario lasciare che{0}i qubit nello stato di errore "ket".</span><span class="sxs-lookup"><span data-stu-id="9512a-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="9512a-206">Possiamo usare @"microsoft.quantum.intrinsic.reset" per riavviare tutti i qubit allo stato zero e questo terminerà la nostra operazione.</span><span class="sxs-lookup"><span data-stu-id="9512a-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


