---
title: Contributo del codice a Microsoft QDK
description: Informazioni su come aggiungere codice di esempio e libreria alla Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7a258a915a807b8e1ee7c2c9c062017d90f6a454
ms.sourcegitcommit: 685a8ab16d7e6a25e63a168d6e7c385fa6e876cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2020
ms.locfileid: "91489766"
---
# <a name="contributing-code"></a><span data-ttu-id="128ac-103">Contributi di codice</span><span class="sxs-lookup"><span data-stu-id="128ac-103">Contributing Code</span></span>

<span data-ttu-id="128ac-104">Oltre a segnalare i problemi e a migliorare la documentazione, il codice aggiunto al quantum Development Kit può essere un metodo molto diretto per aiutare i colleghi nella community di programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="128ac-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="128ac-105">Contribuendo al codice, è possibile risolvere i problemi, fornire nuovi esempi, rendere le librerie esistenti più facili da usare o persino aggiungere funzionalità completamente nuove.</span><span class="sxs-lookup"><span data-stu-id="128ac-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="128ac-106">In questa guida verrà illustrato in dettaglio un po' di ciò che si cerca quando si esaminano le richieste pull per aiutare il contributo a eseguire le operazioni più valide.</span><span class="sxs-lookup"><span data-stu-id="128ac-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="128ac-107">Cosa si cerca</span><span class="sxs-lookup"><span data-stu-id="128ac-107">What We Look For</span></span>

<span data-ttu-id="128ac-108">Un contributo di codice ideale si basa sul lavoro esistente in un repository di Quantum Development Kit per risolvere i problemi, espandere le funzionalità esistenti o aggiungere nuove funzionalità che rientrano nell'ambito di un repository.</span><span class="sxs-lookup"><span data-stu-id="128ac-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="128ac-109">Quando si accetta un contributo del codice, questo diventa parte del kit di sviluppo Quantum stesso, in modo che le nuove funzionalità vengano rilasciate, mantenute e sviluppate nello stesso modo in cui si trova il resto del kit di sviluppo Quantum.</span><span class="sxs-lookup"><span data-stu-id="128ac-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="128ac-110">Pertanto, è utile quando la funzionalità aggiunta da un contributo è ben collaudata e documentata.</span><span class="sxs-lookup"><span data-stu-id="128ac-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="128ac-111">Unit test</span><span class="sxs-lookup"><span data-stu-id="128ac-111">Unit Tests</span></span>

<span data-ttu-id="128ac-112">Le Q# funzioni, le operazioni e i tipi definiti dall'utente che costituiscono librerie come la Canon vengono testati automaticamente come parte dello sviluppo nel repository [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .</span><span class="sxs-lookup"><span data-stu-id="128ac-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="128ac-113">Quando viene aperta una nuova richiesta pull, ad esempio, la configurazione [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) verificherà che le modifiche nella richiesta pull non interrompano le funzionalità esistenti da cui dipende la community di programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="128ac-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="128ac-114">Con la versione più recente Q# , gli unit test vengono definiti usando l' `@Test("QuantumSimulator")` attributo.</span><span class="sxs-lookup"><span data-stu-id="128ac-114">With the latest Q# version, unit tests are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="128ac-115">L'argomento può essere "QuantumSimulator", "ToffoliSimulator", "TraceSimulator" o qualsiasi nome completo che specifichi la destinazione di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="128ac-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the run target.</span></span> <span data-ttu-id="128ac-116">Diversi attributi che definiscono destinazioni di esecuzione diverse possono essere collegati allo stesso oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="128ac-116">Several attributes defining different run targets may be attached to the same callable.</span></span> <span data-ttu-id="128ac-117">Alcuni dei test usano ancora il pacchetto [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) deprecato che espone tutte le Q# funzioni e le operazioni che terminano con `Test` il Framework [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="128ac-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="128ac-118">Questo pacchetto non è più necessario per la definizione degli unit test.</span><span class="sxs-lookup"><span data-stu-id="128ac-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="128ac-119">La funzione seguente viene usata per garantire che le <xref:microsoft.quantum.canon.fst> <xref:microsoft.quantum.canon.snd> funzioni e restituiscano entrambi gli output corretti in un esempio rappresentativo.</span><span class="sxs-lookup"><span data-stu-id="128ac-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="128ac-120">Se l'output di `Fst` o `Snd` non è corretto, l' `fail` istruzione viene usata per evitare che il test abbia esito negativo.</span><span class="sxs-lookup"><span data-stu-id="128ac-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="128ac-121">È possibile controllare le condizioni più complesse usando le tecniche descritte nella [sezione test](xref:microsoft.quantum.libraries.diagnostics) della Guida alle librerie standard.</span><span class="sxs-lookup"><span data-stu-id="128ac-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="128ac-122">Ad esempio, il test seguente controlla che, `H(q); X(q); H(q);` come chiamato da, abbia <xref:microsoft.quantum.canon.applywith> la stessa operazione di `Z(q)` .</span><span class="sxs-lookup"><span data-stu-id="128ac-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="128ac-123">Quando si aggiungono nuove funzionalità, è consigliabile aggiungere anche nuovi test per assicurarsi che il contributo funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="128ac-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="128ac-124">In questo modo il resto della community può gestire e sviluppare la funzionalità e, in particolare, gli altri sviluppatori sanno che possono basarsi sulla propria funzionalità.</span><span class="sxs-lookup"><span data-stu-id="128ac-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="128ac-125">Questa operazione funziona anche in altro modo.</span><span class="sxs-lookup"><span data-stu-id="128ac-125">This works the other way around, too!</span></span>
> <span data-ttu-id="128ac-126">Se è presente una funzionalità esistente in cui mancano alcuni test, l'aggiunta del code coverage dei test comporterebbe un notevole contributo alla community.</span><span class="sxs-lookup"><span data-stu-id="128ac-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="128ac-127">Localmente, è possibile eseguire gli unit test usando Esplora test di Visual Studio o il `dotnet test` comando, in modo che sia possibile controllare il contributo prima di aprire una richiesta pull.</span><span class="sxs-lookup"><span data-stu-id="128ac-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="pull-requests"></a><span data-ttu-id="128ac-128">Richieste pull</span><span class="sxs-lookup"><span data-stu-id="128ac-128">Pull Requests</span></span>

<span data-ttu-id="128ac-129">Quando si è pronti per contribuire al lavoro, inviare una richiesta pull tramite GitHub al repository corrispondente.</span><span class="sxs-lookup"><span data-stu-id="128ac-129">When you are ready to contribute your work, please send a Pull Request via GitHub to the corresponding repository.</span></span>
<span data-ttu-id="128ac-130">Il team verificherà e fornirà commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="128ac-130">The team will review and provide feedback.</span></span> <span data-ttu-id="128ac-131">Tutti i commenti devono essere risolti e risolti e tutti i controlli devono essere superati prima che il codice venga unito al `main` ramo.</span><span class="sxs-lookup"><span data-stu-id="128ac-131">All comments need to be answered and resolved and all checks need to pass before the code is merged to the `main` branch.</span></span>

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="128ac-132">Quando si rifiuterà una richiesta pull</span><span class="sxs-lookup"><span data-stu-id="128ac-132">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="128ac-133">In alcuni casi, la richiesta pull verrà rifiutata per un contributo.</span><span class="sxs-lookup"><span data-stu-id="128ac-133">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="128ac-134">In tal caso, non significa che si tratta di un problema, in quanto esistono diversi motivi per cui potrebbe non essere possibile accettare un particolare contributo.</span><span class="sxs-lookup"><span data-stu-id="128ac-134">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="128ac-135">Probabilmente, più comunemente, un contributo alla community di programmazione quantistica è molto utile, ma i repository di Quantum Development Kit non sono il posto giusto per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="128ac-135">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="128ac-136">In questi casi, è consigliabile fare in modo che il proprio repository---parte della potenza del kit di sviluppo di Quantum sia semplice creare e distribuire librerie personalizzate usando GitHub e NuGet.org, nello stesso modo in cui si distribuiscono oggi le librerie di chimica e canonica.</span><span class="sxs-lookup"><span data-stu-id="128ac-136">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="128ac-137">In altri casi, è possibile rifiutare un contributo valido semplicemente perché non è ancora pronto per la manutenzione e lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="128ac-137">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="128ac-138">Può essere difficile eseguire tutte le operazioni, in modo da pianificare le funzionalità più adatte per lavorare come roadmap.</span><span class="sxs-lookup"><span data-stu-id="128ac-138">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="128ac-139">Questo può essere un altro caso in cui il rilascio di una funzionalità come libreria di terze parti può essere molto utile.</span><span class="sxs-lookup"><span data-stu-id="128ac-139">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="128ac-140">In alternativa, è possibile chiedere all'utente di modificare una funzionalità per adattarla al nostro piano di guida, in modo da poter eseguire le operazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="128ac-140">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="128ac-141">Verranno anche richieste modifiche a una richiesta pull se è necessaria una maggiore documentazione o unit test per facilitarne l'uso o se lo stile è diverso dal resto delle Q# librerie che rende più difficile per gli utenti trovare la propria funzionalità.</span><span class="sxs-lookup"><span data-stu-id="128ac-141">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="128ac-142">In questi casi, si tenterà di offrire un suggerimento per le revisioni del codice sugli elementi che possono essere aggiunti o modificati per facilitare l'inclusione del contributo.</span><span class="sxs-lookup"><span data-stu-id="128ac-142">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="128ac-143">Infine, non è possibile accettare contributi che causino danni alla community di calcolo quantistica, come illustrato nel [codice di comportamento open source di Microsoft](https://opensource.microsoft.com/codeofconduct/).</span><span class="sxs-lookup"><span data-stu-id="128ac-143">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="128ac-144">Vogliamo assicurarci che i contributi soddisfino l'intera community di calcolo quantistica, sia nella sua attuale diversità, che in futuro man mano che cresce per diventare ancora più inclusivo.</span><span class="sxs-lookup"><span data-stu-id="128ac-144">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="128ac-145">Per realizzare questo obiettivo, siamo lieti di aiutarti.</span><span class="sxs-lookup"><span data-stu-id="128ac-145">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="128ac-146">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="128ac-146">Next steps</span></span>

<span data-ttu-id="128ac-147">Grazie per aver contribuito a rendere Quantum Development Kit un'ottima risorsa per l'intera community di programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="128ac-147">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="128ac-148">Per altre informazioni, continuare con la guida seguente sullo Q# stile.</span><span class="sxs-lookup"><span data-stu-id="128ac-148">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="128ac-149">Informazioni sulle Q# linee guida di stile</span><span class="sxs-lookup"><span data-stu-id="128ac-149">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="128ac-150">A seconda del tipo di codice che si sta contribuendo, potrebbe essere necessario tenere presente ulteriori considerazioni che possono contribuire a rendere il contributo più efficace possibile per la community.</span><span class="sxs-lookup"><span data-stu-id="128ac-150">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="128ac-151">Informazioni sugli esempi di contributo</span><span class="sxs-lookup"><span data-stu-id="128ac-151">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
