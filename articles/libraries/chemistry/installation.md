---
title: Installazione e convalida della libreria di chimica | Microsoft Docs
description: Installazione e convalida della libreria di chimica
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184203"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="97155-103">Installazione e convalida della libreria di chimica</span><span class="sxs-lookup"><span data-stu-id="97155-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="97155-104">Quantum Development Kit fornisce il supporto per le applicazioni di chimica quantistica tramite il pacchetto NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .</span><span class="sxs-lookup"><span data-stu-id="97155-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="97155-105">Come per gli altri pacchetti NuGet, è facile aggiungere la libreria di chimica al progetto.</span><span class="sxs-lookup"><span data-stu-id="97155-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="97155-106">**Visual Studio 2019:** Se si usa Visual Studio 2019, è possibile aggiungere i pacchetti di chimica quantistica usando Gestione pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="97155-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="97155-107">Per aprire Gestione pacchetti, fare clic con il pulsante destro del mouse sul progetto a cui si vuole aggiungere la libreria di chimica e selezionare "Gestisci pacchetti NuGet", come nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="97155-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="97155-108">Dalla scheda Sfoglia cercare il nome del pacchetto "Microsoft. Quantum. Chemistry".</span><span class="sxs-lookup"><span data-stu-id="97155-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="97155-109">Assicurarsi di eseguire il segno di "Includi versione preliminare".</span><span class="sxs-lookup"><span data-stu-id="97155-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="97155-110">In questo elenco vengono elencati i pacchetti disponibili per il download.</span><span class="sxs-lookup"><span data-stu-id="97155-110">This will list the packages available for download.</span></span>
<span data-ttu-id="97155-111">Fare clic su "Microsoft. Quantum. Chemistry nel riquadro a sinistra, selezionare la versione provvisoria più recente nel riquadro di destra e fare clic su" Installa ":</span><span class="sxs-lookup"><span data-stu-id="97155-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="97155-112">Per ulteriori informazioni, vedere la [Guida dell'interfaccia utente di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="97155-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="97155-113">In alternativa, è possibile usare la console di gestione pacchetti per aggiungere la libreria Quantum Chemistry al progetto con un'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="97155-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="97155-114">Dalla console di gestione pacchetti eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97155-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="97155-115">Per ulteriori informazioni, vedere la [Guida della console di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="97155-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="97155-116">**Riga di comando o Visual Studio Code:** Usando la riga di comando autonomamente o dall'interno di Visual Studio Code, è possibile usare il comando `dotnet` per aggiungere il riferimento al pacchetto NuGet al progetto:</span><span class="sxs-lookup"><span data-stu-id="97155-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="97155-117">Verifica dell'installazione</span><span class="sxs-lookup"><span data-stu-id="97155-117">Verifying Your Installation</span></span> 

<span data-ttu-id="97155-118">Come il resto del kit di sviluppo Quantum, la libreria Quantum Chemistry comprende una serie di esempi completamente documentati che consentono di iniziare subito a funzionare.</span><span class="sxs-lookup"><span data-stu-id="97155-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="97155-119">Per testare l'installazione usando questi esempi, clonare il [repository main Samples](https://github.com/Microsoft/Quantum), quindi eseguire uno degli esempi.</span><span class="sxs-lookup"><span data-stu-id="97155-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="97155-120">Per eseguire ad esempio il [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) esempio:</span><span class="sxs-lookup"><span data-stu-id="97155-120">For example, to run the [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="97155-121">Per verificare l'installazione della libreria Quantum Chemistry usando Microsoft Visual Studio dopo la clonazione del repository:</span><span class="sxs-lookup"><span data-stu-id="97155-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="97155-122">Aprire la soluzione ChemistrySamples. sln nella cartella chimica.</span><span class="sxs-lookup"><span data-stu-id="97155-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="97155-123">Selezionare Samples/1.</span><span class="sxs-lookup"><span data-stu-id="97155-123">Select Samples/1.</span></span> <span data-ttu-id="97155-124">Semplici molecole/MolecularHydrogen come progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="97155-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="97155-125">Premere F5 per eseguire la demo relativa alla valutazione della fase Quantum a idrogeno molecolare.</span><span class="sxs-lookup"><span data-stu-id="97155-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="97155-126">Per altre informazioni su come stimare i valori dei livelli di energia, vedere [ottenere stime del livello di energia](xref:microsoft.quantum.chemistry.examples.energyestimate) .</span><span class="sxs-lookup"><span data-stu-id="97155-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="97155-127">Uso di Quantum Development Kit con NWChem</span><span class="sxs-lookup"><span data-stu-id="97155-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="97155-128">Nell'esempio MolecularHydrogen vengono utilizzati dati di input molecolari configurati manualmente.</span><span class="sxs-lookup"><span data-stu-id="97155-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="97155-129">Sebbene si tratti di un problema per piccoli esempi, la chimica quantistica su larga scala richiede hamiltonians con milioni o miliardi di termini.</span><span class="sxs-lookup"><span data-stu-id="97155-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="97155-130">Tali hamiltonians, generati da pacchetti di chimica computazionale scalabile, sono troppo grandi per essere importati manualmente.</span><span class="sxs-lookup"><span data-stu-id="97155-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="97155-131">La libreria Quantum Chemistry per Quantum Development Kit è progettata per funzionare correttamente con i pacchetti di chimica computazionale, in particolare la piattaforma chimica computazionale [**nwchem**](http://www.nwchem-sw.org/) sviluppata dal laboratorio Environmental Molecular Science ( EMSL) a Pacific Northwest National Laboratory.</span><span class="sxs-lookup"><span data-stu-id="97155-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="97155-132">In particolare, il pacchetto di `Microsoft.Quantum.Chemistry` fornisce strumenti per il caricamento di istanze di problemi di simulazione della chimica quantistica rappresentati nello [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), supportati anche per l'esportazione da versioni recenti di nwchem.</span><span class="sxs-lookup"><span data-stu-id="97155-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="97155-133">Per iniziare a usare NWChem insieme a Quantum Development Kit, è consigliabile usare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="97155-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="97155-134">Iniziare a usare i file Broombridge esistenti forniti con gli esempi in [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="97155-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="97155-135">Usare il [Generatore di frecce EMSL per la Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , che è un front-end basato sul Web con nwchem, per generare nuovi file di input molecolari in formato Broombridge.</span><span class="sxs-lookup"><span data-stu-id="97155-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="97155-136">Usare l' [immagine Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fornita da PNNL per eseguire nwchem</span><span class="sxs-lookup"><span data-stu-id="97155-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="97155-137">[Compilare nwchem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) per la piattaforma.</span><span class="sxs-lookup"><span data-stu-id="97155-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="97155-138">Vedere [end-to-end con nwchem](xref:microsoft.quantum.chemistry.examples.endtoend) per altre informazioni su come usare nwchem per i modelli chimici per l'analisi con la libreria di chimica Quantum Developers Kit.</span><span class="sxs-lookup"><span data-stu-id="97155-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="97155-139">Introduzione all'uso dei file Broombridge forniti con gli esempi</span><span class="sxs-lookup"><span data-stu-id="97155-139">Getting started using Broombridge files provided with the samples</span></span>
<span data-ttu-id="97155-140">La cartella [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) nel repository di esempi di Quantum Development Kit contiene file di dati di molecole in formato Broombridge.</span><span class="sxs-lookup"><span data-stu-id="97155-140">The [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="97155-141">Come esempio semplice, usare l'esempio di libreria di chimica, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) per caricare l'Hamiltoniana da uno dei file Broombridge ed eseguire stime di controllo della simulazione quantistica algorigthms:</span><span class="sxs-lookup"><span data-stu-id="97155-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="97155-142">Per altre informazioni su come inserire le molecole rappresentate dallo schema Broombridge, vedere [caricamento di un'Hamiltoniana da un file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="97155-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="97155-143">Per altre informazioni sulla stima delle risorse, vedere [ottenere i conteggi delle risorse](xref:microsoft.quantum.chemistry.examples.resourcecounts) .</span><span class="sxs-lookup"><span data-stu-id="97155-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="97155-144">Introduzione all'uso del generatore di frecce EMSL</span><span class="sxs-lookup"><span data-stu-id="97155-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="97155-145">EMSL Arrows è uno strumento che usa NWChem e database di calcolo chimici per generare dati molecolari.</span><span class="sxs-lookup"><span data-stu-id="97155-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="97155-146">[Il generatore di frecce EMSL per il Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) consente di immettere il modello usando più generatori di modelli molecolari e di generare il file di file di Broombridge che verrà usato dal quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="97155-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="97155-147">Dalla pagina EMSL, fare clic sulla scheda [' instuctions '] e seguire le istruzioni [' simple examples '] per generare file Broombridge.</span><span class="sxs-lookup"><span data-stu-id="97155-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="97155-148">Provare quindi a eseguire [' GetGateCount '] per visualizzare le stime delle risorse Quantum per queste molecole.</span><span class="sxs-lookup"><span data-stu-id="97155-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="97155-149">Installazione di NWChem dall'origine</span><span class="sxs-lookup"><span data-stu-id="97155-149">Installing NWChem from Source</span></span>

<span data-ttu-id="97155-150">Le istruzioni complete su come installare NWChem dall'origine [sono fornite da PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="97155-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="97155-151">Se si vuole usare NWChem da Windows 10, il sottosistema Windows per Linux è un'ottima opzione.</span><span class="sxs-lookup"><span data-stu-id="97155-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="97155-152">Dopo aver installato [Ubuntu 18,04 LTS per Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), eseguire `ubuntu18.04` dal terminale preferito e seguire le istruzioni riportate sopra per installare nwchem dall'origine.</span><span class="sxs-lookup"><span data-stu-id="97155-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="97155-153">Dopo aver compilato NWChem dall'origine, è possibile eseguire lo script `yaml_driver` fornito con NWChem per produrre rapidamente istanze di Broombridge dai Deck di input di NWChem:</span><span class="sxs-lookup"><span data-stu-id="97155-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="97155-154">Questo comando creerà un nuovo file di `input.yaml` nel formato Broombridge all'interno della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="97155-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="97155-155">Uso di NWChem con Docker</span><span class="sxs-lookup"><span data-stu-id="97155-155">Using NWChem with Docker</span></span>

<span data-ttu-id="97155-156">Le immagini predefinite per l'uso di NWChem sono disponibili tra piattaforme diverse tramite l' [Hub Docker](https://hub.docker.com).</span><span class="sxs-lookup"><span data-stu-id="97155-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="97155-157">Per iniziare, seguire le istruzioni di installazione di Docker per la piattaforma:</span><span class="sxs-lookup"><span data-stu-id="97155-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="97155-158">Installare Docker per Ubuntu</span><span class="sxs-lookup"><span data-stu-id="97155-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="97155-159">Installare Docker per macOS</span><span class="sxs-lookup"><span data-stu-id="97155-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="97155-160">Installare Docker per Windows 10</span><span class="sxs-lookup"><span data-stu-id="97155-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="97155-161">Se si usa Docker per Windows, sarà necessario condividere l'unità che contiene la directory temporanea (in genere si tratta dell'unità `C:\`) con il daemon docker.</span><span class="sxs-lookup"><span data-stu-id="97155-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="97155-162">Per altri dettagli, vedere la [documentazione di Docker](https://docs.docker.com/docker-for-windows/#shared-drives) .</span><span class="sxs-lookup"><span data-stu-id="97155-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="97155-163">Una volta installato Docker, è possibile usare il modulo di PowerShell fornito con gli esempi di Quantum Development Kit per eseguire l'immagine oppure è possibile eseguire l'immagine manualmente.</span><span class="sxs-lookup"><span data-stu-id="97155-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="97155-164">Qui viene illustrato in dettaglio l'uso di PowerShell. Se si vuole usare manualmente l'immagine Docker, vedere la [documentazione fornita con l'immagine](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="97155-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="97155-165">Esecuzione di NWChem tramite PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="97155-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="97155-166">Per usare l'immagine Docker NWChem con Quantum Development Kit, viene fornito un modulo di PowerShell di piccole dimensioni che gestisce automaticamente i file in e da NWChem.</span><span class="sxs-lookup"><span data-stu-id="97155-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="97155-167">Se PowerShell Core non è ancora installato, è possibile scaricarlo multipiattaforma dal [repository di PowerShell su GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="97155-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="97155-168">PowerShell core viene usato anche per alcuni esempi per illustrare l'interoperabilità con data science e flussi di lavoro di analisi business.</span><span class="sxs-lookup"><span data-stu-id="97155-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="97155-169">Dopo aver installato PowerShell core, importare `InvokeNWChem.psm1` per rendere disponibili i comandi NWChem nella sessione corrente:</span><span class="sxs-lookup"><span data-stu-id="97155-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="97155-170">In questo modo il comando `Convert-NWChemToBroombridge` verrà reso disponibile nella sessione corrente di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97155-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="97155-171">Per scaricare le immagini necessarie da Docker e usarle per eseguire i deck di input NWChem e acquisire l'output in Broombridge, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97155-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="97155-172">Verrà creato un file Broombridge eseguendo NWChem in `input.nw`.</span><span class="sxs-lookup"><span data-stu-id="97155-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="97155-173">Per impostazione predefinita, l'output di Broombridge avrà lo stesso nome e percorso del deck di input, con l'estensione `.nw` sostituita da `.yaml`.</span><span class="sxs-lookup"><span data-stu-id="97155-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="97155-174">Questa operazione può essere sottoposta a override utilizzando il parametro `-DestinationPath` per `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="97155-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="97155-175">Per ottenere altre informazioni, è possibile usare la funzionalità integrata della Guida di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="97155-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```


