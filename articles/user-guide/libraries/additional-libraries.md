---
title: 'Uso di librerie Q # aggiuntive'
description: 'Informazioni su come aggiungere librerie Q # aggiuntive alle applicazioni Quantum.'
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
ms.openlocfilehash: b82113b925870d07c8a28aecd50176e009826062
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872635"
---
# <a name="using-additional-q-libraries"></a><span data-ttu-id="e653d-103">Uso di librerie Q # aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e653d-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="e653d-104">Quantum Development Kit fornisce funzionalità aggiuntive specifiche del dominio tramite i _pacchetti NuGet_ che è possibile aggiungere ai progetti Q #.</span><span class="sxs-lookup"><span data-stu-id="e653d-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="e653d-105">Libreria Q #</span><span class="sxs-lookup"><span data-stu-id="e653d-105">Q# Library</span></span>  | <span data-ttu-id="e653d-106">Pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="e653d-106">NuGet package</span></span> | <span data-ttu-id="e653d-107">Note</span><span class="sxs-lookup"><span data-stu-id="e653d-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="e653d-108">Libreria standard Q #</span><span class="sxs-lookup"><span data-stu-id="e653d-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="e653d-109">**Microsoft. Quantum. standard**</span><span class="sxs-lookup"><span data-stu-id="e653d-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="e653d-110">Inclusa per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="e653d-110">Included by default</span></span> |
| [<span data-ttu-id="e653d-111">Libreria di chimica quantistica</span><span class="sxs-lookup"><span data-stu-id="e653d-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="e653d-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="e653d-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="e653d-113">Libreria per il calcolo numerico quantistico</span><span class="sxs-lookup"><span data-stu-id="e653d-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="e653d-114">**Microsoft. Quantum. Numerics**</span><span class="sxs-lookup"><span data-stu-id="e653d-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="e653d-115">Libreria di apprendimento automatico quantistico</span><span class="sxs-lookup"><span data-stu-id="e653d-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="e653d-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="e653d-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="e653d-117">Una volta installato Quantum Development Kit per l'uso con l'ambiente preferito e il linguaggio host, è possibile aggiungere facilmente librerie a singoli progetti Q # senza ulteriori installazioni.</span><span class="sxs-lookup"><span data-stu-id="e653d-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="e653d-118">Alcune librerie Q # possono funzionare correttamente con strumenti aggiuntivi che funzionano insieme ai programmi Q # o che si integrano con le applicazioni host.</span><span class="sxs-lookup"><span data-stu-id="e653d-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="e653d-119">Ad esempio, le [istruzioni di installazione della libreria di chimica](xref:microsoft.quantum.chemistry.concepts.installation) descrivono come usare il [pacchetto **Microsoft. Quantum. Chemistry** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) con la piattaforma chimica computazionale nwchem e come installare gli `qdk-chem` strumenti da riga di comando per l'utilizzo di dati di chimica quantistica.</span><span class="sxs-lookup"><span data-stu-id="e653d-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="q-command-line-applications-or-net-interopability"></a>[<span data-ttu-id="e653d-120">Applicazioni da riga di comando Q # o interoperabilità .NET</span><span class="sxs-lookup"><span data-stu-id="e653d-120">Q# command-line applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="e653d-121">**Riga di comando o Visual Studio Code:** Usando la riga di comando autonomamente o dall'interno di Visual Studio Code, è possibile usare il `dotnet` comando per aggiungere un riferimento al pacchetto NuGet al progetto.</span><span class="sxs-lookup"><span data-stu-id="e653d-121">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="e653d-122">Ad esempio, per aggiungere il pacchetto [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e653d-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="e653d-123">**Visual Studio:** Se si usa Visual Studio 2019 o versione successiva, è possibile aggiungere altri pacchetti Q # usando Gestione pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="e653d-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="e653d-124">Per caricare un pacchetto:</span><span class="sxs-lookup"><span data-stu-id="e653d-124">To load a package:</span></span> 
1. <span data-ttu-id="e653d-125">Con un progetto aperto in Visual Studio, scegliere **Gestisci pacchetti NuGet** dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="e653d-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="e653d-126">Fare clic su **Sfoglia**, selezionare **Includi versione preliminare** e cercare il nome del pacchetto "Microsoft. Quantum. Numerics".</span><span class="sxs-lookup"><span data-stu-id="e653d-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="e653d-127">In questo elenco vengono elencati i pacchetti disponibili per il download.</span><span class="sxs-lookup"><span data-stu-id="e653d-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="e653d-128">Passare il mouse su **Microsoft. Quantum. Numerics** e fare clic sulla freccia rivolta verso il basso a destra del numero di versione per installare il pacchetto Numerics.</span><span class="sxs-lookup"><span data-stu-id="e653d-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="e653d-129">Per ulteriori informazioni, vedere la [Guida dell'interfaccia utente di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="e653d-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="e653d-130">In alternativa, è possibile usare la console di gestione pacchetti per aggiungere la libreria Numerics al progetto tramite l'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e653d-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Usare la console di gestione pacchetti dalla riga di comando](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="e653d-132">Dalla console di gestione pacchetti eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e653d-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="e653d-133">Per ulteriori informazioni, vedere la [Guida della console di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="e653d-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="iq-notebooks"></a>[<span data-ttu-id="e653d-134">Notebook IQ #</span><span class="sxs-lookup"><span data-stu-id="e653d-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="e653d-135">È possibile rendere disponibili pacchetti aggiuntivi da usare in un notebook IQ # usando il [ `%package` comando Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).</span><span class="sxs-lookup"><span data-stu-id="e653d-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="e653d-136">Ad esempio, per aggiungere il pacchetto [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) da usare in un notebook IQ #, eseguire il comando seguente in una cella del notebook:</span><span class="sxs-lookup"><span data-stu-id="e653d-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="e653d-137">Dopo questo comando, il pacchetto è disponibile per tutte le celle all'interno del notebook.</span><span class="sxs-lookup"><span data-stu-id="e653d-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="e653d-138">Per rendere il pacchetto disponibile dal codice Q # nell'area di lavoro corrente, ricaricare l'area di lavoro dopo aver aggiunto il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="e653d-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="e653d-139">Interoperabilità di Python</span><span class="sxs-lookup"><span data-stu-id="e653d-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="e653d-140">È possibile rendere disponibili pacchetti aggiuntivi da usare in un programma host Python usando il [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) metodo.</span><span class="sxs-lookup"><span data-stu-id="e653d-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="e653d-141">Ad esempio, per aggiungere il pacchetto [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) da usare in un notebook IQ #, eseguire il codice Python seguente:</span><span class="sxs-lookup"><span data-stu-id="e653d-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="e653d-142">Dopo questo comando, il pacchetto verrà reso disponibile per qualsiasi codice Q # compilato usando `qsharp.compile` .</span><span class="sxs-lookup"><span data-stu-id="e653d-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="e653d-143">Per rendere il pacchetto disponibile dal codice Q # nell'area di lavoro corrente, ricaricare l'area di lavoro dopo aver aggiunto il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="e653d-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
