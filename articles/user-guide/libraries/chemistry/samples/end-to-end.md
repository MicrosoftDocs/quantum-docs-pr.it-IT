---
title: Programma Quantum NWChem di esempio
description: Usando un deck di input NWChem, esaminare un esempio di come ottenere i conteggi dei Gate per la simulazione della chimica quantistica.
author: cgranade
ms.author: chgranad
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: 986ff2c2ff144c57bd01ddeea0467d0168fd9334
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835758"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="79ea8-103">End-to-end con NWChem</span><span class="sxs-lookup"><span data-stu-id="79ea8-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="79ea8-104">Questo articolo illustra un esempio di come ottenere i conteggi dei Gate per la simulazione della chimica quantistica, a partire da un deck di input di [nwchem](http://www.nwchem-sw.org/index.php/Main_Page) .</span><span class="sxs-lookup"><span data-stu-id="79ea8-104">In this article, you will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="79ea8-105">Prima di procedere con questo esempio, assicurarsi di avere installato Docker, seguendo la Guida all' [installazione e alla convalida](xref:microsoft.quantum.chemistry.concepts.installation).</span><span class="sxs-lookup"><span data-stu-id="79ea8-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="79ea8-106">Per altre informazioni:</span><span class="sxs-lookup"><span data-stu-id="79ea8-106">For more information:</span></span>
- [<span data-ttu-id="79ea8-107">Struttura dei deck di input NWChem</span><span class="sxs-lookup"><span data-stu-id="79ea8-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="79ea8-108">Comandi del deck di input da usare con Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="79ea8-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [<span data-ttu-id="79ea8-109">Installazione della libreria di chimica e delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="79ea8-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="79ea8-110">Conteggio delle risorse</span><span class="sxs-lookup"><span data-stu-id="79ea8-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="79ea8-111">Questo esempio richiede l'esecuzione di Windows PowerShell core.</span><span class="sxs-lookup"><span data-stu-id="79ea8-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="79ea8-112">Scaricare PowerShell core per Windows, macOS o Linux all'indirizzo https://github.com/PowerShell/PowerShell .</span><span class="sxs-lookup"><span data-stu-id="79ea8-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="79ea8-113">Importazione di moduli di PowerShell necessari</span><span class="sxs-lookup"><span data-stu-id="79ea8-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="79ea8-114">Se non è già stato fatto, clonare il [repository Microsoft/Quantum](https://github.com/Microsoft/Quantum), che contiene esempi e utilità per l'uso di Quantum Development Kit:</span><span class="sxs-lookup"><span data-stu-id="79ea8-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="79ea8-115">Dopo aver clonato `Microsoft/Quantum` , eseguire `cd` la `utilities/` cartella e importare il modulo di PowerShell per l'uso di Docker e nwchem:</span><span class="sxs-lookup"><span data-stu-id="79ea8-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="79ea8-116">Per impostazione predefinita, Windows impedisce l'esecuzione di qualsiasi script o modulo come misura di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="79ea8-116">By default, Windows prevents the running of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="79ea8-117">Per consentire `Invoke-NWChem.psm1` l'esecuzione di moduli in Windows, potrebbe essere necessario modificare i criteri.</span><span class="sxs-lookup"><span data-stu-id="79ea8-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the policy.</span></span>
> <span data-ttu-id="79ea8-118">A tale scopo, eseguire il `Set-ExecutionPolicy` comando:</span><span class="sxs-lookup"><span data-stu-id="79ea8-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="79ea8-119">Il criterio verrà ripristinato quando si esce da PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79ea8-119">The policy will revert when you exit PowerShell.</span></span>
> <span data-ttu-id="79ea8-120">Se si desidera salvare il criterio, utilizzare un valore diverso per `-Scope` :</span><span class="sxs-lookup"><span data-stu-id="79ea8-120">If you would like to save the policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="79ea8-121">A questo punto dovrebbe essere `Convert-NWChemToBroombridge` disponibile il comando:</span><span class="sxs-lookup"><span data-stu-id="79ea8-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="79ea8-122">Si importerà quindi il `Get-GateCount` comando fornito con l'esempio **GetGateCount** .</span><span class="sxs-lookup"><span data-stu-id="79ea8-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="79ea8-123">Per informazioni complete, vedere le [istruzioni fornite con l'esempio](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="79ea8-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).</span></span>
<span data-ttu-id="79ea8-124">Eseguire quindi il comando seguente, sostituendo `<runtime>` con `win10-x64` , `osx-x64` o `linux-x64` , a seconda del sistema operativo in uso:</span><span class="sxs-lookup"><span data-stu-id="79ea8-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="79ea8-125">A questo punto dovrebbe essere `Get-GateCount` disponibile il comando:</span><span class="sxs-lookup"><span data-stu-id="79ea8-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="79ea8-126">Deck di input</span><span class="sxs-lookup"><span data-stu-id="79ea8-126">Input Decks</span></span> ##

<span data-ttu-id="79ea8-127">Il pacchetto NWChem accetta un file di testo denominato _mazzo di input_ che specifica un problema di chimica quantistica da risolvere, insieme ad altri parametri, ad esempio le impostazioni di allocazione della memoria.</span><span class="sxs-lookup"><span data-stu-id="79ea8-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="79ea8-128">Per questo esempio verrà usato uno dei deck di input predefiniti forniti con NWChem.</span><span class="sxs-lookup"><span data-stu-id="79ea8-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="79ea8-129">Innanzitutto, clonare il [repository nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):</span><span class="sxs-lookup"><span data-stu-id="79ea8-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="79ea8-130">Poiché si tratta di un repository di grandi dimensioni, è possibile eseguire un clone superficiale per risparmiare spazio su disco e larghezza di banda, usando l' `--depth 1` argomento.</span><span class="sxs-lookup"><span data-stu-id="79ea8-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="79ea8-131">Questa operazione è tuttavia facoltativa.</span><span class="sxs-lookup"><span data-stu-id="79ea8-131">This is optional, however.</span></span>
> <span data-ttu-id="79ea8-132">La clonazione funzionerà senza alcun problema `--depth 1` .</span><span class="sxs-lookup"><span data-stu-id="79ea8-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="79ea8-133">Il `nwchemgit/nwchem` repository è costituito da diversi Deck di input destinati all'uso con Quantum Development Kit, elencati nella [ `QA/chem_library_tests` cartella](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).</span><span class="sxs-lookup"><span data-stu-id="79ea8-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).</span></span>
<span data-ttu-id="79ea8-134">Per questo esempio verrà usato il deck di `H4` input:</span><span class="sxs-lookup"><span data-stu-id="79ea8-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="79ea8-135">La molecola in questione è un sistema di 4 atomi idrogeno disposti in una determinata geometria che dipende da un angolo, il parametro `alpha` come indicato nel nome `h4_sto6g_alpha.nw` del mazzo.</span><span class="sxs-lookup"><span data-stu-id="79ea8-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="79ea8-136">H4 è un [benchmark molecolare](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) noto per la chimica computazionale dal 1970.</span><span class="sxs-lookup"><span data-stu-id="79ea8-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="79ea8-137">Il parametro `sto6g` indica che il deck implementa una rappresentazione rispetto a un orbitale di tipo Slater, in particolare una rappresentazione rispetto a un set di [base di i-ng](https://en.wikipedia.org/wiki/STO-nG_basis_sets) con 6 funzioni di base gaussiana.</span><span class="sxs-lookup"><span data-stu-id="79ea8-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="79ea8-138">Questo deck di input contiene inoltre diverse istruzioni per il motore di contratti di NWChem tensore che indirizza NWChem a produrre le informazioni necessarie per l'interoperabilità con Quantum Development Kit:</span><span class="sxs-lookup"><span data-stu-id="79ea8-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="79ea8-139">Produzione e utilizzo dell'output Broombridge da NWChem</span><span class="sxs-lookup"><span data-stu-id="79ea8-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="79ea8-140">Sono ora disponibili tutti gli elementi necessari per produrre e utilizzare documenti Broombridge.</span><span class="sxs-lookup"><span data-stu-id="79ea8-140">You now have everything you need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="79ea8-141">Per eseguire NWChem e produrre un documento Broombridge per il `h4_sto6g_0.000.nw` mazzo di input, eseguire `Convert-NWChemToBroombridge` :</span><span class="sxs-lookup"><span data-stu-id="79ea8-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="79ea8-142">La prima volta che si esegue questo comando, Docker Scarica l' `nwchemorg/nwchem-qc` immagine per l'utente.</span><span class="sxs-lookup"><span data-stu-id="79ea8-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="79ea8-143">Questa operazione può richiedere alcuni minuti, a seconda della velocità di connessione, offrendo possibilmente un'opportunità per ottenere una tazza di caffè.</span><span class="sxs-lookup"><span data-stu-id="79ea8-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="79ea8-144">Verrà generato un documento Broombridge denominato `h4_sto6g_0.000.yaml` che è possibile usare con `Get-GateCount` :</span><span class="sxs-lookup"><span data-stu-id="79ea8-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that you can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="79ea8-145">Verrà visualizzato l'output della console che contiene la stima delle risorse, ad esempio il conteggio T, il numero di rotazioni, il numero di CNOT e così via, per vari metodi di simulazione Quantum:</span><span class="sxs-lookup"><span data-stu-id="79ea8-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="79ea8-146">Di seguito sono riportate alcune operazioni da eseguire:</span><span class="sxs-lookup"><span data-stu-id="79ea8-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="79ea8-147">Provare diversi Deck di input predefiniti, ad esempio variando il parametro `alpha` in `h4_sto6g_alpha.nw`</span><span class="sxs-lookup"><span data-stu-id="79ea8-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="79ea8-148">Provare a modificare i deck modificando direttamente i deck NWChem, ad esempio esplorando i `STO-nG` modelli per diverse opzioni di n,</span><span class="sxs-lookup"><span data-stu-id="79ea8-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="79ea8-149">Provare altri deck di input NWChem predefiniti disponibili in `nwchem/qa/chem_library_tests` ,</span><span class="sxs-lookup"><span data-stu-id="79ea8-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="79ea8-150">Provare una suite di benchmark Broombridge YAML predefiniti che sono stati generati da NWChem e sono disponibili come parte del [repository Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="79ea8-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="79ea8-151">Questi benchmark includono:</span><span class="sxs-lookup"><span data-stu-id="79ea8-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="79ea8-152">molecole piccole, ad esempio idrogeno molecolare (H2), berillio (be), litio idruro (LiH),</span><span class="sxs-lookup"><span data-stu-id="79ea8-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="79ea8-153">molecole più grandi, ad esempio Ozone (O3), Beta-Carotone, citosina e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="79ea8-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="79ea8-154">Provare le [frecce EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) front-end grafiche che dispongono di un'interfaccia per la Microsoft Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="79ea8-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="79ea8-155">Generazione dell'output Broombridge dalle frecce EMSL</span><span class="sxs-lookup"><span data-stu-id="79ea8-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="79ea8-156">Per iniziare a usare le frecce EMSL front-end basate sul Web, esplorare un browser [qui](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span><span class="sxs-lookup"><span data-stu-id="79ea8-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="79ea8-157">L'esecuzione di frecce EMSL in un Web browser richiede l'abilitazione di JavaScript.</span><span class="sxs-lookup"><span data-stu-id="79ea8-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="79ea8-158">Per informazioni su come abilitare JavaScript nel browser, fare riferimento a queste [istruzioni](https://www.enable-javascript.com/) .</span><span class="sxs-lookup"><span data-stu-id="79ea8-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="79ea8-159">Per prima cosa, immettere una molecola nella casella query con il testo seguente: ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="79ea8-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="79ea8-160">È possibile immettere molte molecole in base al nome familiare, ad esempio "caffeina" anziché "1, 3, 7-Trimethylxanthine".</span><span class="sxs-lookup"><span data-stu-id="79ea8-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="79ea8-161">Quindi, fare clic sul pulsante che indica ``theory{qsharp_chem}`` .</span><span class="sxs-lookup"><span data-stu-id="79ea8-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="79ea8-162">Questa operazione consente di popolare ulteriormente la finestra di query con un'istruzione che indica all'esecuzione di esportare l'output nel formato YAML di Broombridge.</span><span class="sxs-lookup"><span data-stu-id="79ea8-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="79ea8-163">Ora, clock on ``Run Arrows`` .</span><span class="sxs-lookup"><span data-stu-id="79ea8-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="79ea8-164">A seconda delle dimensioni dell'input, l'operazione potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="79ea8-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="79ea8-165">In alternativa, nel caso in cui il modello specifico sia già stato calcolato in precedenza, è possibile eseguire la stessa operazione in modo estremamente rapido, in quanto sarà sufficiente per una ricerca in un database.</span><span class="sxs-lookup"><span data-stu-id="79ea8-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="79ea8-166">In entrambi i casi, si passerà a una nuova pagina che contiene una pletora di informazioni sulla particolare esecuzione di NWChem sul deck specificato dall'input.</span><span class="sxs-lookup"><span data-stu-id="79ea8-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="79ea8-167">È possibile scaricare e salvare il file YAML Broombridge dalla sezione che inizia con l'intestazione seguente:</span><span class="sxs-lookup"><span data-stu-id="79ea8-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="79ea8-168">Fare clic su on ``download`` , che consente di salvare una copia locale con un nome file univoco, ad esempio ``qsharp_chem48443.yaml`` (il nome specifico sarà diverso per ogni esecuzione).</span><span class="sxs-lookup"><span data-stu-id="79ea8-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="79ea8-169">È quindi possibile elaborare ulteriormente il file come sopra, ad esempio con</span><span class="sxs-lookup"><span data-stu-id="79ea8-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="79ea8-170">per ottenere i conteggi delle risorse.</span><span class="sxs-lookup"><span data-stu-id="79ea8-170">to get resource counts.</span></span> 

<span data-ttu-id="79ea8-171">È possibile utilizzare il generatore di molecole 3D a cui è possibile accedere dalla ``Arrows Entry - 3D Builder`` scheda della pagina iniziale delle frecce EMSL.</span><span class="sxs-lookup"><span data-stu-id="79ea8-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="79ea8-172">Se si fa clic sull'immagine [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D della molecola visualizzata, sarà possibile modificarla.</span><span class="sxs-lookup"><span data-stu-id="79ea8-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="79ea8-173">È possibile spostare gli atomi, trascinare gli atomi in modo da modificare le distanze intermolecolari, aggiungere/rimuovere atomi e così via. Per ognuna di queste opzioni, una volta aggiunto ``theory{qsharp_chem}`` nella casella query, è possibile generare un'istanza dello schema YAML di Broombridge ed esaminarla ulteriormente usando la libreria Quantum Chemistry.</span><span class="sxs-lookup"><span data-stu-id="79ea8-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
