---
title: Contributi agli esempi di Microsoft QDK
description: Informazioni su come aggiungere codice di esempio al Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0c940a4cf228c694a899988f469158b1bb6e2425
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847592"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="a37c7-103">Contributi agli esempi per Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="a37c7-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="a37c7-104">Se si è interessati a contribuire al codice nel [repository di esempi](https://github.com/Microsoft/Quantum), grazie per aver reso la community di sviluppo quantistica un posto migliore.</span><span class="sxs-lookup"><span data-stu-id="a37c7-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="a37c7-105">Repository degli esempi di Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="a37c7-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="a37c7-106">Per facilitare la preparazione del contributo per facilitare il più possibile, è utile esaminare rapidamente la disposizione del repository di esempi:</span><span class="sxs-lookup"><span data-stu-id="a37c7-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="a37c7-107">Ovvero, gli esempi nel [repository Microsoft/Quantum](https://github.com/microsoft/Quantum) vengono suddivisi in base all'area di interesse in cartelle diverse, ad esempio `algorithms/` , `arithmetic/` o `characterization/` .</span><span class="sxs-lookup"><span data-stu-id="a37c7-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="a37c7-108">All'interno della cartella per ogni area di interesse, ogni esempio è costituito da una singola cartella che raccoglie tutti gli elementi necessari a un utente per esplorare e utilizzare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="a37c7-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="a37c7-109">Struttura degli esempi</span><span class="sxs-lookup"><span data-stu-id="a37c7-109">How Samples are Structured</span></span>

<span data-ttu-id="a37c7-110">Esaminando i file che compongono ogni cartella, è consigliabile approfondire l' [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) esempio.</span><span class="sxs-lookup"><span data-stu-id="a37c7-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="a37c7-111">File</span><span class="sxs-lookup"><span data-stu-id="a37c7-111">File</span></span>              | <span data-ttu-id="a37c7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a37c7-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="a37c7-113">Q# progetto utilizzato per compilare l'esempio con la .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="a37c7-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="a37c7-114">Q# operazioni e funzioni per l'esempio</span><span class="sxs-lookup"><span data-stu-id="a37c7-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="a37c7-115">Programma host C# usato per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a37c7-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="a37c7-116">Programma host Python usato per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="a37c7-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="a37c7-117">Documentazione su cosa fa l'esempio e su come usarlo</span><span class="sxs-lookup"><span data-stu-id="a37c7-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="a37c7-118">Non tutti gli esempi avranno esattamente lo stesso set di file (ad esempio, alcuni esempi possono essere solo C#, altri potrebbero non avere un host Python o alcuni esempi potrebbero richiedere l'uso di file di dati auxillary).</span><span class="sxs-lookup"><span data-stu-id="a37c7-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="a37c7-119">Anatomia di un file Leggimi utile</span><span class="sxs-lookup"><span data-stu-id="a37c7-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="a37c7-120">Un file particolarmente importante, tuttavia, è il `README.md` file, in quanto gli utenti devono iniziare a usare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="a37c7-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="a37c7-121">Ognuno `README.md` deve iniziare con alcuni metadati che consentono a docs.Microsoft.com/samples di trovare il contributo.</span><span class="sxs-lookup"><span data-stu-id="a37c7-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a37c7-122">Vedere come viene eseguito il rendering dell'esempio chsh-Game</span><span class="sxs-lookup"><span data-stu-id="a37c7-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="a37c7-123">Questi metadati vengono forniti come [intestazione YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) che indica le lingue analizzate dall'esempio (in genere, questo sarà `qsharp` , `csharp` e `python` ) e i prodotti trattati dall'esempio (in genere, solo `qdk` ).</span><span class="sxs-lookup"><span data-stu-id="a37c7-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="a37c7-124">`page_type: sample`Per visualizzare l'esempio in docs.Microsoft.com/samples, è necessario specificare la chiave nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="a37c7-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="a37c7-125">Analogamente, `product` le `language` chiavi e sono fondamentali per aiutare gli utenti a trovare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="a37c7-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="a37c7-126">Successivamente, è utile fornire una breve introduzione che indichi il risultato del nuovo esempio:</span><span class="sxs-lookup"><span data-stu-id="a37c7-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="a37c7-127">Gli utenti dell'esempio apprezzeranno anche la conoscenza di ciò che è necessario per eseguirlo (ad esempio, gli utenti hanno bisogno solo del quantum Development Kit o di software aggiuntivo, ad esempio node.js?):</span><span class="sxs-lookup"><span data-stu-id="a37c7-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="a37c7-128">In questo modo, è possibile indicare agli utenti come eseguire l'esempio:</span><span class="sxs-lookup"><span data-stu-id="a37c7-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="a37c7-129">Infine, è utile indicare agli utenti la funzione di ogni file nell'esempio e dove possono andare per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="a37c7-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="a37c7-130">Assicurarsi di usare gli URL assoluti qui, poiché l'esempio verrà visualizzato in un altro URL quando viene eseguito il rendering in docs.microsoft.com/samples.</span><span class="sxs-lookup"><span data-stu-id="a37c7-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
