---
title: Contributo del codice | Microsoft Docs
description: Contributo del codice
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: cca50e6c63d4bb982aa5f0a59fc19d08ecbec508
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185903"
---
# <a name="contributing-code"></a><span data-ttu-id="f69e2-103">Contributo del codice</span><span class="sxs-lookup"><span data-stu-id="f69e2-103">Contributing Code</span></span> #

<span data-ttu-id="f69e2-104">Oltre a segnalare i problemi e a migliorare la documentazione, il codice aggiunto al quantum Development Kit può essere un metodo molto diretto per aiutare i colleghi nella community di programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="f69e2-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="f69e2-105">Contribuendo al codice, è possibile risolvere i problemi, fornire nuovi esempi, rendere le librerie esistenti più facili da usare o persino aggiungere funzionalità completamente nuove.</span><span class="sxs-lookup"><span data-stu-id="f69e2-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="f69e2-106">In questa guida verrà illustrato in dettaglio un po' di ciò che si cerca quando si esaminano le richieste pull per aiutare il contributo a eseguire le operazioni più valide.</span><span class="sxs-lookup"><span data-stu-id="f69e2-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="f69e2-107">Cosa si cerca</span><span class="sxs-lookup"><span data-stu-id="f69e2-107">What We Look For</span></span> ##

<span data-ttu-id="f69e2-108">Un contributo di codice ideale si basa sul lavoro esistente in un repository di Quantum Development Kit per risolvere i problemi, espandere le funzionalità esistenti o aggiungere nuove funzionalità che rientrano nell'ambito di un repository.</span><span class="sxs-lookup"><span data-stu-id="f69e2-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="f69e2-109">Quando si accetta un contributo del codice, questo diventa parte del kit di sviluppo Quantum stesso, in modo che le nuove funzionalità vengano rilasciate, mantenute e sviluppate nello stesso modo in cui si trova il resto del kit di sviluppo Quantum.</span><span class="sxs-lookup"><span data-stu-id="f69e2-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="f69e2-110">Pertanto, è utile quando la funzionalità aggiunta da un contributo è ben collaudata e documentata.</span><span class="sxs-lookup"><span data-stu-id="f69e2-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="f69e2-111">Unit test</span><span class="sxs-lookup"><span data-stu-id="f69e2-111">Unit Tests</span></span> ###

<span data-ttu-id="f69e2-112">Le funzioni, le operazioni e i tipi definiti dall'utente di Q # che costituiscono librerie come il canone vengono testati automaticamente come parte dello sviluppo nel repository [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .</span><span class="sxs-lookup"><span data-stu-id="f69e2-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="f69e2-113">Quando viene aperta una nuova richiesta pull, ad esempio, la configurazione [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) verificherà che le modifiche nella richiesta pull non interrompano le funzionalità esistenti da cui dipende la community di programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="f69e2-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>
<span data-ttu-id="f69e2-114">Questi test vengono scritti usando il pacchetto [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) , che espone le funzioni e le operazioni Q # come test per il Framework [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="f69e2-114">These tests are written using the [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package, which exposes Q# functions and operations as tests for the [xUnit](https://xunit.github.io/) framework.</span></span>

<span data-ttu-id="f69e2-115">Il [`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) usa questa integrazione xUnit per eseguire qualsiasi funzione o operazione che termina con `Test`.</span><span class="sxs-lookup"><span data-stu-id="f69e2-115">The [`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) uses this xUnit integration to run any functions or operations ending in `Test`.</span></span>
<span data-ttu-id="f69e2-116">Ad esempio, la funzione seguente viene usata per garantire che le funzioni <xref:microsoft.quantum.canon.fst> e <xref:microsoft.quantum.canon.snd> restituiscono entrambi gli output corretti in un esempio rappresentativo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-116">For instance, the following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="f69e2-117">Se l'output di `Fst` o `Snd` non è corretto, viene utilizzata l'istruzione `fail` per impedire che il test abbia esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-117">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
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

<span data-ttu-id="f69e2-118">È possibile controllare le condizioni più complesse usando le tecniche descritte nella [sezione test](xref:microsoft.quantum.libraries.diagnostics) della Guida alle librerie standard.</span><span class="sxs-lookup"><span data-stu-id="f69e2-118">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="f69e2-119">Ad esempio, il test seguente controlla che `H(q); X(q); H(q);` come chiamato da <xref:microsoft.quantum.canon.applywith> esegue la stessa operazione `Z(q)`.</span><span class="sxs-lookup"><span data-stu-id="f69e2-119">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```qsharp
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="f69e2-120">Quando si aggiungono nuove funzionalità, è consigliabile aggiungere anche nuovi test per assicurarsi che il contributo funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="f69e2-120">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="f69e2-121">In questo modo il resto della community può gestire e sviluppare la funzionalità e, in particolare, gli altri sviluppatori sanno che possono basarsi sulla propria funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f69e2-121">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="f69e2-122">Questa operazione funziona anche in altro modo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-122">This works the other way around, too!</span></span>
> <span data-ttu-id="f69e2-123">Se è presente una funzionalità esistente in cui mancano alcuni test, l'aggiunta del code coverage dei test comporterebbe un notevole contributo alla community.</span><span class="sxs-lookup"><span data-stu-id="f69e2-123">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="f69e2-124">Localmente, gli unit test possono essere eseguiti con Esplora test di Visual Studio o con il comando `dotnet test`, in modo che sia possibile controllare il contributo prima di aprire una richiesta pull.</span><span class="sxs-lookup"><span data-stu-id="f69e2-124">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="f69e2-125">Quando si rifiuterà una richiesta pull</span><span class="sxs-lookup"><span data-stu-id="f69e2-125">When We'll Reject a Pull Request</span></span> ##

<span data-ttu-id="f69e2-126">In alcuni casi, la richiesta pull verrà rifiutata per un contributo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-126">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="f69e2-127">In tal caso, non significa che si tratta di un problema, in quanto esistono diversi motivi per cui potrebbe non essere possibile accettare un particolare contributo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-127">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="f69e2-128">Probabilmente, più comunemente, un contributo alla community di programmazione quantistica è molto utile, ma i repository di Quantum Development Kit non sono il posto giusto per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-128">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="f69e2-129">In questi casi, è consigliabile fare in modo che il proprio repository---parte della potenza del kit di sviluppo di Quantum sia semplice creare e distribuire librerie personalizzate usando GitHub e NuGet.org, nello stesso modo in cui si distribuiscono la canonica e la chimica librerie attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="f69e2-129">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="f69e2-130">In altri casi, è possibile rifiutare un contributo valido semplicemente perché non è ancora pronto per la manutenzione e lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-130">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="f69e2-131">Può essere difficile eseguire tutte le operazioni, in modo da pianificare le funzionalità più adatte per lavorare come roadmap.</span><span class="sxs-lookup"><span data-stu-id="f69e2-131">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="f69e2-132">Questo può essere un altro caso in cui il rilascio di una funzionalità come libreria di terze parti può essere molto utile.</span><span class="sxs-lookup"><span data-stu-id="f69e2-132">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="f69e2-133">In alternativa, è possibile chiedere all'utente di modificare una funzionalità per adattarla al nostro piano di guida, in modo da poter eseguire le operazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="f69e2-133">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="f69e2-134">Verranno anche richieste modifiche a una richiesta pull se è necessaria una maggiore documentazione o unit test per facilitarne l'uso o se lo stile è diverso dal resto delle librerie Q # che rende più difficile per gli utenti trovare la propria funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f69e2-134">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="f69e2-135">In questi casi, si tenterà di offrire un suggerimento per le revisioni del codice sugli elementi che possono essere aggiunti o modificati per facilitare l'inclusione del contributo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-135">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="f69e2-136">Infine, non è possibile accettare contributi che causino danni alla community di calcolo quantistica, come illustrato nel [codice di comportamento open source di Microsoft](https://opensource.microsoft.com/codeofconduct/).</span><span class="sxs-lookup"><span data-stu-id="f69e2-136">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="f69e2-137">Vogliamo assicurarci che i contributi soddisfino l'intera community di calcolo quantistica, sia nella sua attuale diversità, che in futuro man mano che cresce per diventare ancora più inclusivo.</span><span class="sxs-lookup"><span data-stu-id="f69e2-137">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="f69e2-138">Per realizzare questo obiettivo, siamo lieti di aiutarti.</span><span class="sxs-lookup"><span data-stu-id="f69e2-138">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f69e2-139">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f69e2-139">Next steps</span></span> ##

<span data-ttu-id="f69e2-140">Grazie per aver contribuito a rendere Quantum Development Kit un'ottima risorsa per l'intera community di programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="f69e2-140">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="f69e2-141">Per altre informazioni, continuare con la guida seguente sullo stile Q #.</span><span class="sxs-lookup"><span data-stu-id="f69e2-141">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f69e2-142">Informazioni sulle linee guida di stile Q #</span><span class="sxs-lookup"><span data-stu-id="f69e2-142">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)
