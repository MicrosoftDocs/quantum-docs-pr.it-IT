---
title: 'Tutti insieme-tecniche Q # | Microsoft Docs'
description: 'Riunendoli-tecniche Q #'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820165"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="23005-103">Riunendoli: Teleporting</span><span class="sxs-lookup"><span data-stu-id="23005-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="23005-104">Torniamo all'esempio del circuito di Teleporting definito nei [circuiti Quantum](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="23005-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="23005-105">Questa operazione verrà usata per illustrare i concetti appresi finora.</span><span class="sxs-lookup"><span data-stu-id="23005-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="23005-106">Di seguito è riportata una spiegazione del teleportamento del quantum per coloro che non hanno familiarità con la teoria, seguito da una procedura dettagliata dell'implementazione del codice in Q #.</span><span class="sxs-lookup"><span data-stu-id="23005-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="23005-107">Teleportation Quantum: teoria</span><span class="sxs-lookup"><span data-stu-id="23005-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="23005-108">La teleportazione quantistica è una tecnica per l'invio di uno stato quantum sconosciuto (a cui si farà riferimento come "__messaggio__") da un qubit in una posizione a una qubit in un'altra posizione (si farà riferimento a questi qubits rispettivamente come '__here__' è__There__').</span><span class="sxs-lookup"><span data-stu-id="23005-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="23005-109">È possibile rappresentare il __messaggio__ come vettore usando la notazione Dirac:</span><span class="sxs-lookup"><span data-stu-id="23005-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="23005-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="23005-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="23005-111">Lo stato del __messaggio__ qubit non è noto perché non sono noti i valori di $ \Alpha $ e $ \beta $.</span><span class="sxs-lookup"><span data-stu-id="23005-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="23005-112">Passaggio 1: creare uno stato incastrato</span><span class="sxs-lookup"><span data-stu-id="23005-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="23005-113">Per inviare il __messaggio__ __, è__necessario che __il qubit sia presente in questo punto__ di qubit.</span><span class="sxs-lookup"><span data-stu-id="23005-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="23005-114">Questa operazione viene eseguita applicando un Hadamard Gate, seguito da un CNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="23005-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="23005-115">Esaminiamo i calcoli alla base di queste operazioni Gate.</span><span class="sxs-lookup"><span data-stu-id="23005-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="23005-116">Si inizierà con il qubits in __questo__ punto e __ci__ si troverà entrambi nello stato $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="23005-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="23005-117">Dopo aver coinvolto questi qubits, si trovano nello stato:</span><span class="sxs-lookup"><span data-stu-id="23005-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="23005-118">$ $ \ket{\Phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="23005-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="23005-119">Passaggio 2: inviare il messaggio</span><span class="sxs-lookup"><span data-stu-id="23005-119">Step 2: Send the message</span></span>
<span data-ttu-id="23005-120">Per inviare il __messaggio__ , viene prima di tutto applicato un CNOT Gate con il __messaggio__ qubit e __qui__ qubit come input (il __messaggio__ qubit è il controllo e __qui__ qubit è il qubit di destinazione, in questa istanza).</span><span class="sxs-lookup"><span data-stu-id="23005-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="23005-121">È possibile scrivere questo stato di input:</span><span class="sxs-lookup"><span data-stu-id="23005-121">This input state can be written:</span></span>

<span data-ttu-id="23005-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="23005-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="23005-123">Questa operazione si espande a:</span><span class="sxs-lookup"><span data-stu-id="23005-123">This expands to:</span></span>

<span data-ttu-id="23005-124">$ $ \ket{\psi}\ket{\Phi ^ +} = \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="23005-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="23005-125">Come promemoria, il CNOT Gate capovolge il qubit di destinazione quando il controllo qubit è 1.</span><span class="sxs-lookup"><span data-stu-id="23005-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="23005-126">Quindi, ad esempio, un input di $ \ket{000}$ non comporterà alcuna modifica, perché il primo qubit (il controllo) è 0.</span><span class="sxs-lookup"><span data-stu-id="23005-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="23005-127">Tuttavia, se il primo qubit è 1, ad esempio un input di $ \ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="23005-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="23005-128">In questo caso, l'output è $ \ket{110}$ come il secondo qubit (la destinazione) viene capovolto dal CNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="23005-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="23005-129">Si consideri ora l'output dopo che CNOT Gate ha agito sull'input precedente.</span><span class="sxs-lookup"><span data-stu-id="23005-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="23005-130">Il risultato è:</span><span class="sxs-lookup"><span data-stu-id="23005-130">The result is:</span></span>

<span data-ttu-id="23005-131">$ $ \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="23005-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="23005-132">Il passaggio successivo per inviare il __messaggio__ consiste nell'applicare un Hadamard Gate al __messaggio__ qubit (il primo qubit di ogni termine).</span><span class="sxs-lookup"><span data-stu-id="23005-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="23005-133">Come promemoria, il Hadamard Gate esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="23005-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="23005-134">Input</span><span class="sxs-lookup"><span data-stu-id="23005-134">Input</span></span> | <span data-ttu-id="23005-135">Output</span><span class="sxs-lookup"><span data-stu-id="23005-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="23005-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="23005-136">$\ket{0}$</span></span>  | <span data-ttu-id="23005-137">$ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="23005-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="23005-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="23005-138">$\ket{1}$</span></span>  | <span data-ttu-id="23005-139">$ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="23005-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="23005-140">Se si applica il Hadamard Gate alla prima qubit di ogni termine dell'output precedente, viene visualizzato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="23005-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="23005-141">$ $ \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="23005-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="23005-142">Si noti che ogni termine ha $2 \frac{1}{\sqrt{2}} $ factors.</span><span class="sxs-lookup"><span data-stu-id="23005-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="23005-143">Possiamo moltiplicarli per ottenere il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="23005-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="23005-144">$ $ \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="23005-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="23005-145">Il{1}$ \frac {2}$ Factor è comune a ogni termine, quindi è ora possibile utilizzarlo all'esterno delle parentesi quadre:</span><span class="sxs-lookup"><span data-stu-id="23005-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="23005-146">$ $ \frac{1}{2}\Big [\Alpha (\ket{0} + \ket{1}) \ket{00} + \Alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\Big] $ $</span><span class="sxs-lookup"><span data-stu-id="23005-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="23005-147">Possiamo quindi moltiplicare le parentesi per ogni termine fornendo:</span><span class="sxs-lookup"><span data-stu-id="23005-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="23005-148">$ $ \frac{1}{2}\Big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\Big] $ $</span><span class="sxs-lookup"><span data-stu-id="23005-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="23005-149">Passaggio 3: misurare il risultato</span><span class="sxs-lookup"><span data-stu-id="23005-149">Step 3: Measure the result</span></span>

<span data-ttu-id="23005-150">A causa di questo __errore, qualsiasi__ misurazione in __questa__ posizione influirà sullo __stato.__</span><span class="sxs-lookup"><span data-stu-id="23005-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="23005-151">Se misuriamo il primo e il secondo qubit (__Message__ e __here__) possiamo scoprire quale stato è __presente__ in, a causa di questa proprietà dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="23005-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="23005-152">Se misuriamo e otteniamo un risultato 00, la superposizione viene compressa, lasciando solo i termini coerenti con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="23005-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="23005-153">Questo è $ \alpha\ket{000} + \beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="23005-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="23005-154">Questa operazione può essere sottoposta a refactoring in $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="23005-155">Pertanto, se misuriamo il primo e il secondo qubit a 00, sappiamo che il terzo qubit è __presente__nello stato $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="23005-156">Se si misura e si ottiene un risultato 01, la superposizione viene compressa, lasciando solo i termini coerenti con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="23005-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="23005-157">Questo è $ \alpha\ket{011} + \beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="23005-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="23005-158">Questa operazione può essere sottoposta a refactoring in $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="23005-159">Pertanto __, se__misuriamo il primo e il secondo qubit come 01, sappiamo che il terzo qubit è nello stato $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="23005-160">Se misuriamo e otteniamo il risultato 10, la superposizione viene compressa, lasciando solo i termini coerenti con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="23005-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="23005-161">Questo è $ \alpha\ket{100}-\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="23005-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="23005-162">Questa operazione può essere sottoposta a refactoring in $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="23005-163">Pertanto __, se__misuriamo il primo e il secondo qubit come 10, sappiamo che il terzo qubit è nello stato $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="23005-164">Se misuriamo e otteniamo il risultato 11, la superposizione viene compressa, lasciando solo i termini coerenti con questo risultato.</span><span class="sxs-lookup"><span data-stu-id="23005-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="23005-165">Questo è $ \alpha\ket{111}-\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="23005-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="23005-166">Questa operazione può essere sottoposta a refactoring in $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="23005-167">Pertanto, se misuriamo il primo e il secondo qubit come 11, sappiamo che il terzo qubit, __c'__ è nello stato $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="23005-168">Passaggio 4: interpretare il risultato</span><span class="sxs-lookup"><span data-stu-id="23005-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="23005-169">Come promemoria, il __messaggio__ originale che avremmo voluto inviare era:</span><span class="sxs-lookup"><span data-stu-id="23005-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="23005-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="23005-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="23005-171">Dobbiamo ottenere lo __stato qubit in__ questo stato, in modo che lo stato ricevuto sia quello desiderato.</span><span class="sxs-lookup"><span data-stu-id="23005-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="23005-172">Se è stato misurato e ottenuto un risultato pari a __00, il__terzo qubit è nello stato $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="23005-173">Poiché si tratta del __messaggio__previsto, non è necessaria alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="23005-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="23005-174">Se è stato misurato e ottenuto il risultato di __01, il__terzo qubit è nello stato $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="23005-175">Questo comportamento è diverso rispetto al __messaggio__previsto, tuttavia l'applicazione di un controllo not consente di ottenere lo stato desiderato $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="23005-176">Se è stato misurato e ottenuto il risultato di __10, il__terzo qubit è nello stato $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="23005-177">Questo comportamento è diverso da quello __previsto,__ tuttavia l'applicazione di uno Z Gate indica lo stato desiderato $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="23005-178">Se è stato misurato e ottenuto il risultato di __11, il__terzo qubit è nello stato $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="23005-179">Questo comportamento è diverso da quello __previsto,__ tuttavia l'applicazione di un controllo not seguito da un Gate Z indica lo stato desiderato $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="23005-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="23005-180">Per riepilogare, se si misura e il primo qubit è 1, viene applicato un controllo Z.</span><span class="sxs-lookup"><span data-stu-id="23005-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="23005-181">Se misuriamo e il secondo qubit è 1, viene applicato un NOT Gate.</span><span class="sxs-lookup"><span data-stu-id="23005-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="23005-182">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="23005-182">Summary</span></span>
<span data-ttu-id="23005-183">Di seguito è riportato un circuito Quantum del libro di testo che implementa la teleportazione.</span><span class="sxs-lookup"><span data-stu-id="23005-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="23005-184">Se si passa da sinistra a destra, è possibile vedere:</span><span class="sxs-lookup"><span data-stu-id="23005-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="23005-185">Passaggio 1: eseguire __questa__ __operazione applicando__ un Hadamard Gate e CNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="23005-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="23005-186">Passaggio 2: invio del __messaggio__ tramite CNOT Gate e Hadamard Gate.</span><span class="sxs-lookup"><span data-stu-id="23005-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="23005-187">Passaggio 3: esecuzione di una misurazione del primo e del secondo qubits, __messaggio__ e __qui__.</span><span class="sxs-lookup"><span data-stu-id="23005-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="23005-188">Passaggio 4: applicazione di una funzione NOT Gate o Z Gate, a seconda del risultato della misurazione nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="23005-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' Teleport (msg: qubit, there: qubit): unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="23005-190">Teleportation Quantum: codice</span><span class="sxs-lookup"><span data-stu-id="23005-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="23005-191">Abbiamo il nostro circuito per la teleportazione quantistica:</span><span class="sxs-lookup"><span data-stu-id="23005-191">We have our circuit for quantum teleportation:</span></span>

![' Teleport (msg: qubit, there: qubit): unit '](~/media/teleportation.svg)

<span data-ttu-id="23005-193">È ora possibile tradurre ogni passaggio in questo circuito Quantum in Q #.</span><span class="sxs-lookup"><span data-stu-id="23005-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="23005-194">Passaggio 0: definizione</span><span class="sxs-lookup"><span data-stu-id="23005-194">Step 0: Definition</span></span>
<span data-ttu-id="23005-195">Quando si esegue la teleportazione, è necessario essere a conoscenza del __messaggio__ che si vuole inviare e__del punto in__cui si vuole inviarlo.</span><span class="sxs-lookup"><span data-stu-id="23005-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="23005-196">Per questo motivo, si inizia definendo una nuova operazione Teleport a cui vengono assegnati due qubits come argomenti, `msg` e `there`:</span><span class="sxs-lookup"><span data-stu-id="23005-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="23005-197">È anche necessario allocare un `here` qubit che viene raggiunto con un blocco `using`:</span><span class="sxs-lookup"><span data-stu-id="23005-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="23005-198">Passaggio 1: creare uno stato incastrato</span><span class="sxs-lookup"><span data-stu-id="23005-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="23005-199">È quindi possibile creare una coppia di `here` e `there` con le operazioni di @"microsoft.quantum.intrinsic.h" e @"microsoft.quantum.intrinsic.cnot":</span><span class="sxs-lookup"><span data-stu-id="23005-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="23005-200">Passaggio 2: inviare il messaggio</span><span class="sxs-lookup"><span data-stu-id="23005-200">Step 2: Send the message</span></span>
<span data-ttu-id="23005-201">Si utilizzeranno quindi i successivi $ \operatorname{CNOT} $ e $H $ Gates per spostare il messaggio qubit:</span><span class="sxs-lookup"><span data-stu-id="23005-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="23005-202">Passaggio 3 & 4: misurazione e interpretazione del risultato</span><span class="sxs-lookup"><span data-stu-id="23005-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="23005-203">Infine, si usa @"microsoft.quantum.intrinsic.m" per eseguire le misurazioni ed eseguire le operazioni Gate necessarie per ottenere lo stato desiderato, come indicato dalle istruzioni `if`:</span><span class="sxs-lookup"><span data-stu-id="23005-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="23005-204">Termina la definizione dell'operatore di Teleporting, in modo da poter deallocare `here`, terminare il corpo e terminare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="23005-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
