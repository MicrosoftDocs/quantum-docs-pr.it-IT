---
title: Apertura delle richieste pull
description: Informazioni su come inviare una richiesta pull di GitHub quando si è pronti per contribuire al codice o alla documentazione per la Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: a4373a65688893c95e0475356c8f6fca0912f8c5
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907461"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="0c493-103">Apertura di richieste pull</span><span class="sxs-lookup"><span data-stu-id="0c493-103">Opening Pull Requests</span></span> #

<span data-ttu-id="0c493-104">Tutta la documentazione relativa a Quantum Development Kit viene gestita con il sistema di controllo della versione di git tramite l'uso di diversi repository ospitati in GitHub.</span><span class="sxs-lookup"><span data-stu-id="0c493-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="0c493-105">L'uso di git e GitHub insieme semplifica la collaborazione in Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="0c493-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="0c493-106">In particolare, tutti i repository git possono essere clonati o biforcati per creare una copia completamente indipendente del repository.</span><span class="sxs-lookup"><span data-stu-id="0c493-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="0c493-107">In questo modo è possibile lavorare sul proprio contributo con gli strumenti e con i ritmi preferiti.</span><span class="sxs-lookup"><span data-stu-id="0c493-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="0c493-108">Quando si è pronti, è possibile inviare una richiesta per includere il contributo nei repository, usando la funzionalità delle _richieste pull_ di GitHub.</span><span class="sxs-lookup"><span data-stu-id="0c493-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="0c493-109">La pagina per ogni richiesta pull include i dettagli di tutte le modifiche apportate al contributo, un elenco di commenti sul contributo e un set di strumenti di revisione che possono essere usati da altri membri della community per fornire commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="0c493-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="0c493-110">Anche se un'esercitazione completa su git esula dall'ambito di questa guida, è possibile suggerire i collegamenti seguenti per altre risorse sull'apprendimento di git:</span><span class="sxs-lookup"><span data-stu-id="0c493-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="0c493-111">[Informazioni su git](https://www.atlassian.com/git): un set di esercitazioni git da Atlassian.</span><span class="sxs-lookup"><span data-stu-id="0c493-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="0c493-112">[Controllo della versione in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): Guida su come usare Visual Studio Code come GUI per git.</span><span class="sxs-lookup"><span data-stu-id="0c493-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="0c493-113">[Lab Learning di GitHub](https://lab.github.com/): un set di corsi online per l'uso di Git, GitHub e delle tecnologie correlate.</span><span class="sxs-lookup"><span data-stu-id="0c493-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="0c493-114">[Visualizzazione di git](https://git-school.github.io/visualizing-git/): strumento interattivo per visualizzare il modo in cui i comandi Git cambiano lo stato di un repository.</span><span class="sxs-lookup"><span data-stu-id="0c493-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="0c493-115">[Controllo della versione con git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): esercitazione git orientata al calcolo scientifico.</span><span class="sxs-lookup"><span data-stu-id="0c493-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="0c493-116">[Informazioni sulle diramazioni di git](https://learngitbranching.js.org/): un set interattivo di diramazioni e ribasare i puzzle per apprendere le nuove funzionalità di git.</span><span class="sxs-lookup"><span data-stu-id="0c493-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="0c493-117">Che cos'è una richiesta pull?</span><span class="sxs-lookup"><span data-stu-id="0c493-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="0c493-118">Detto quanto sopra, è utile richiedere alcuni istanti per indicare **la richiesta di**pull.</span><span class="sxs-lookup"><span data-stu-id="0c493-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="0c493-119">Quando si usa Git, tutte le modifiche vengono rappresentate come _commit_ che descrivono il modo in cui tali modifiche sono correlate allo stato del repository prima di tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="0c493-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="0c493-120">Spesso si disegnano diagrammi in cui i commit vengono disegnati come cerchi con frecce dei commit precedenti.</span><span class="sxs-lookup"><span data-stu-id="0c493-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="0c493-121">Si supponga di avere avviato un contributo in un _ramo_ denominato `feature`.</span><span class="sxs-lookup"><span data-stu-id="0c493-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="0c493-122">Il fork di **Microsoft/Quantum** potrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0c493-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![Un ramo di lavoro in GitHub](~/media/git-workflow-step0.png)

<span data-ttu-id="0c493-124">Se si apportano le modifiche nel repository locale, è possibile effettuare il _pull_ delle modifiche da un altro repository nel proprio per recuperare le modifiche apportate a upstream.</span><span class="sxs-lookup"><span data-stu-id="0c493-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![Pull e Unione di modifiche da un repository upstream](~/media/git-workflow-step1.png)

<span data-ttu-id="0c493-126">Le richieste pull funzionano allo stesso modo, ma in senso inverso: quando si apre una richiesta pull, si chiede al repository upstream di effettuare il pull del contributo in.</span><span class="sxs-lookup"><span data-stu-id="0c493-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![Richiesta di eseguire il pull delle modifiche nel repository originale](~/media/git-workflow-step2.png)

<span data-ttu-id="0c493-128">Quando si apre una richiesta pull a uno dei repository, GitHub offrirà agli altri utenti della community la possibilità di visualizzare un riepilogo delle modifiche apportate, di commentarle e di fornire suggerimenti su come contribuire a migliorare ulteriormente il contributo.</span><span class="sxs-lookup"><span data-stu-id="0c493-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![Screenshot di una richiesta pull in GitHub](~/media/pull-request-header.png)

<span data-ttu-id="0c493-130">L'uso di questo processo consente di usare la funzionalità GitHub per migliorare i contributi e mantenere un prodotto di alta qualità per la community di programmazione quantistica.</span><span class="sxs-lookup"><span data-stu-id="0c493-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="0c493-131">Come effettuare una richiesta pull</span><span class="sxs-lookup"><span data-stu-id="0c493-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="0c493-132">Esistono due modi principali per effettuare una richiesta pull.</span><span class="sxs-lookup"><span data-stu-id="0c493-132">There are two main ways to make a pull request.</span></span>
<span data-ttu-id="0c493-133">Per le piccole modifiche che influiscono solo su un singolo file, è possibile usare l'interfaccia Web GitHub per creare una richiesta pull interamente online.</span><span class="sxs-lookup"><span data-stu-id="0c493-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span>
<span data-ttu-id="0c493-134">Per i contributi più complessi, è più spesso facile usare il computer locale per preparare prima una richiesta pull.</span><span class="sxs-lookup"><span data-stu-id="0c493-134">For more complicated contributions, it's most often easier to use your local computer to prepare for a pull request first.</span></span>

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a><span data-ttu-id="0c493-135">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0c493-135">Next steps</span></span> ##

<span data-ttu-id="0c493-136">Congratulazioni per aver usato git per aiutare la community di Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="0c493-136">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="0c493-137">Per altre informazioni su come contribuire al codice, continuare con la guida seguente.</span><span class="sxs-lookup"><span data-stu-id="0c493-137">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0c493-138">Informazioni su come contribuire al codice</span><span class="sxs-lookup"><span data-stu-id="0c493-138">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
