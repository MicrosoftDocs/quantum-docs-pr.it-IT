---
title: Aggiornare Quantum Development Kit (QDK)
description: Descrive come aggiornare i progetti Q# e Microsoft Quantum Development Kit alla versione corrente.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 457083ea4756d64375834e5a276c2d91031138fe
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885142"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="75577-103">Aggiornare Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="75577-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="75577-104">Informazioni su come aggiornare Microsoft Quantum Development Kit (QDK) all'ultima versione.</span><span class="sxs-lookup"><span data-stu-id="75577-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="75577-105">In questo articolo si presuppone che il QDK sia già installato.</span><span class="sxs-lookup"><span data-stu-id="75577-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="75577-106">Se si tratta della prima installazione, vedere la [guida all'installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="75577-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="75577-107">È consigliabile usare sempre la versione più recente del QDK.</span><span class="sxs-lookup"><span data-stu-id="75577-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="75577-108">Seguire questa guida all'aggiornamento per eseguire l'aggiornamento alla versione più recente del QDK.</span><span class="sxs-lookup"><span data-stu-id="75577-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="75577-109">Il processo è articolato in due parti:</span><span class="sxs-lookup"><span data-stu-id="75577-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="75577-110">Aggiornamento dei file e dei progetti Q# esistenti per allineare il codice all'eventuale sintassi aggiornata.</span><span class="sxs-lookup"><span data-stu-id="75577-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="75577-111">Aggiornamento del QDK stesso per l'ambiente di sviluppo scelto.</span><span class="sxs-lookup"><span data-stu-id="75577-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="75577-112">Aggiornamento dei progetti Q#</span><span class="sxs-lookup"><span data-stu-id="75577-112">Updating Q# Projects</span></span> 

<span data-ttu-id="75577-113">Indipendentemente dal fatto che si usi C# o Python per ospitare le operazioni Q#, seguire queste istruzioni per aggiornare i progetti Q#.</span><span class="sxs-lookup"><span data-stu-id="75577-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="75577-114">In primo luogo, verificare di avere la versione più recente di [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="75577-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="75577-115">Eseguire il comando seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="75577-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="75577-116">Verificare che l'output sia un valore pari o superiore a `3.1.100`.</span><span class="sxs-lookup"><span data-stu-id="75577-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="75577-117">In caso contrario, installare la [versione più recente](https://dotnet.microsoft.com/download) e ripetere la verifica.</span><span class="sxs-lookup"><span data-stu-id="75577-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="75577-118">Attenersi quindi alle istruzioni seguenti, a seconda della configurazione (Visual Studio, Visual Studio Code o direttamente dalla riga di comando).</span><span class="sxs-lookup"><span data-stu-id="75577-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="75577-119">Aggiornare progetti Q# in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75577-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="75577-120">Eseguire l'aggiornamento alla versione più recente di Visual Studio 2019. Per le istruzioni, vedere [qui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="75577-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="75577-121">Aprire la soluzione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75577-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="75577-122">Nel menu selezionare **Compila** -> **Pulisci soluzione**.</span><span class="sxs-lookup"><span data-stu-id="75577-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="75577-123">In ognuno dei file con estensione csproj aggiornare il framework di destinazione a `netcoreapp3.1` o a `netstandard2.1` se si tratta di un progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="75577-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="75577-124">Questo significa modificare le righe nel formato:</span><span class="sxs-lookup"><span data-stu-id="75577-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="75577-125">Per altre informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="75577-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="75577-126">In ognuno dei file con estensione csproj impostare l'SDK su `Microsoft.Quantum.Sdk`, come indicato nella riga seguente.</span><span class="sxs-lookup"><span data-stu-id="75577-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="75577-127">Si noti che il numero di versione deve essere l'ultimo disponibile. Per determinarlo, esaminare le [note sulla versione](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="75577-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="75577-128">Salvare e chiudere tutti i file della soluzione.</span><span class="sxs-lookup"><span data-stu-id="75577-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="75577-129">Selezionare **Strumenti** -> **Riga di comando** -> **Prompt dei comandi per gli sviluppatori**.</span><span class="sxs-lookup"><span data-stu-id="75577-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="75577-130">In alternativa, è possibile usare la console di gestione pacchetti in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75577-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="75577-131">Per ogni progetto nella soluzione eseguire il comando seguente per **rimuovere** questo pacchetto:</span><span class="sxs-lookup"><span data-stu-id="75577-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="75577-132">Se i progetti usano qualsiasi altro pacchetto Microsoft.Quantum o Microsoft.Azure.Quantum, ad esempio Microsoft.Quantum.Numerics, eseguire il comando **Aggiungi** per aggiornare la versione usata per tali pacchetti.</span><span class="sxs-lookup"><span data-stu-id="75577-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="75577-133">Chiudere il prompt dei comandi e selezionare **Compila** -> **Compila soluzione** (*non* selezionare Ricompila soluzione).</span><span class="sxs-lookup"><span data-stu-id="75577-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="75577-134">È ora possibile procedere con l'[aggiornamento dell'estensione Visual Studio QDK](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="75577-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="75577-135">Aggiornare progetti Q# in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="75577-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="75577-136">In Visual Studio Code aprire la cartella contenente il progetto da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="75577-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="75577-137">Selezionare **Terminale** -> **Nuovo terminale**.</span><span class="sxs-lookup"><span data-stu-id="75577-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="75577-138">Seguire le istruzioni per l'aggiornamento con la riga di comando riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="75577-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="75577-139">Aggiornare i progetti Q# con la riga di comando</span><span class="sxs-lookup"><span data-stu-id="75577-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="75577-140">Passare alla cartella contenente il file di progetto principale.</span><span class="sxs-lookup"><span data-stu-id="75577-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="75577-141">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="75577-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="75577-142">Determinare la versione corrente del QDK.</span><span class="sxs-lookup"><span data-stu-id="75577-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="75577-143">Per trovarla, è possibile esaminare le [note sulla versione](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="75577-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="75577-144">La versione è indicata in un formato simile a `0.11.2006.207`.</span><span class="sxs-lookup"><span data-stu-id="75577-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="75577-145">In ognuno dei file `.csproj` seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="75577-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="75577-146">Aggiornare il framework di destinazione a `netcoreapp3.1` o a `netstandard2.1` se si tratta di un progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="75577-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="75577-147">Questo significa modificare le righe nel formato:</span><span class="sxs-lookup"><span data-stu-id="75577-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="75577-148">Per altre informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="75577-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="75577-149">Sostituire il riferimento all'SDK nella definizione del progetto.</span><span class="sxs-lookup"><span data-stu-id="75577-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="75577-150">Assicurarsi che il numero di versione corrisponda al valore determinato nel **passaggio 3**.</span><span class="sxs-lookup"><span data-stu-id="75577-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="75577-151">Rimuovere il riferimento al pacchetto `Microsoft.Quantum.Development.Kit`, se presente, che verrà specificato nella voce seguente:</span><span class="sxs-lookup"><span data-stu-id="75577-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="75577-152">Aggiornare la versione di tutti i pacchetti Microsoft Quantum alla versione rilasciata più di recente del QDK (determinata nel **passaggio 3**).</span><span class="sxs-lookup"><span data-stu-id="75577-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="75577-153">I nomi dei pacchetti sono conformi ai criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="75577-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="75577-154">I riferimenti ai pacchetti hanno il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="75577-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="75577-155">Salvare il file aggiornato.</span><span class="sxs-lookup"><span data-stu-id="75577-155">Save the updated file.</span></span>

    - <span data-ttu-id="75577-156">Ripristinare le dipendenze del progetto eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="75577-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="75577-157">Tornare alla cartella contenente il progetto principale ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="75577-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="75577-158">Dopo aver completato l'aggiornamento dei progetti Q#, attenersi alle istruzioni seguenti per aggiornare il QDK stesso.</span><span class="sxs-lookup"><span data-stu-id="75577-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="75577-159">Aggiornamento del QDK</span><span class="sxs-lookup"><span data-stu-id="75577-159">Updating the QDK</span></span>

<span data-ttu-id="75577-160">Il processo per aggiornare il QDK varia a seconda del linguaggio di sviluppo e dell'ambiente usati.</span><span class="sxs-lookup"><span data-stu-id="75577-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="75577-161">Selezionare l'ambiente di sviluppo di seguito.</span><span class="sxs-lookup"><span data-stu-id="75577-161">Select your development environment below.</span></span>

* [<span data-ttu-id="75577-162">Python: aggiornare il pacchetto `qsharp`</span><span class="sxs-lookup"><span data-stu-id="75577-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="75577-163">Notebook di Jupyter: aggiornare il kernel IQ#</span><span class="sxs-lookup"><span data-stu-id="75577-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="75577-164">Visual Studio: aggiornare l'estensione QDK</span><span class="sxs-lookup"><span data-stu-id="75577-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="75577-165">VS Code: aggiornare l'estensione QDK</span><span class="sxs-lookup"><span data-stu-id="75577-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="75577-166">Riga di comando e C#: aggiornare i modelli di progetto</span><span class="sxs-lookup"><span data-stu-id="75577-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="75577-167">Aggiornare il pacchetto Python `qsharp`</span><span class="sxs-lookup"><span data-stu-id="75577-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="75577-168">La procedura di aggiornamento varia a seconda che l'installazione originale sia stata eseguita con conda o con l'interfaccia della riga di comando .NET e pip.</span><span class="sxs-lookup"><span data-stu-id="75577-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="75577-169">Aggiornamento con conda (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="75577-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="75577-170">Attivare l'ambiente conda in cui è stato installato il pacchetto `qsharp` e quindi eseguire questo comando per aggiornarlo:</span><span class="sxs-lookup"><span data-stu-id="75577-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="75577-171">Eseguire il comando seguente dal percorso dei file `.qs`:</span><span class="sxs-lookup"><span data-stu-id="75577-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="75577-172">Aggiornamento con l'interfaccia della riga di comando .NET e pip (opzione avanzata)</span><span class="sxs-lookup"><span data-stu-id="75577-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="75577-173">Aggiornare il kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="75577-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="75577-174">Verificare la versione di `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="75577-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="75577-175">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="75577-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20070124
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="75577-176">Non importa se la versione di `iqsharp` in uso è superiore.</span><span class="sxs-lookup"><span data-stu-id="75577-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="75577-177">Deve corrispondere all'[ultima versione](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="75577-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="75577-178">Aggiornare il pacchetto `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="75577-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="75577-179">Verificare la versione di `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="75577-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="75577-180">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="75577-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.20070124
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="75577-181">Eseguire il comando seguente dal percorso dei file `.qs`:</span><span class="sxs-lookup"><span data-stu-id="75577-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="75577-182">È ora possibile usare il pacchetto Python `qsharp` aggiornato per eseguire i programmi quantistici esistenti.</span><span class="sxs-lookup"><span data-stu-id="75577-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-iq-jupyter-kernel"></a><span data-ttu-id="75577-183">Aggiornare li kernel IQ# per Jupyter</span><span class="sxs-lookup"><span data-stu-id="75577-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="75577-184">La procedura di aggiornamento varia a seconda che l'installazione originale sia stata eseguita con conda o con l'interfaccia della riga di comando .NET e pip.</span><span class="sxs-lookup"><span data-stu-id="75577-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="75577-185">Aggiornamento con conda (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="75577-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="75577-186">Attivare l'ambiente conda in cui è stato installato il pacchetto `qsharp` e quindi eseguire questo comando per aggiornarlo:</span><span class="sxs-lookup"><span data-stu-id="75577-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="75577-187">Eseguire il comando seguente da una cella in ogni notebook di Jupyter Q# esistente:</span><span class="sxs-lookup"><span data-stu-id="75577-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="75577-188">Aggiornamento con l'interfaccia della riga di comando .NET e pip (opzione avanzata)</span><span class="sxs-lookup"><span data-stu-id="75577-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="75577-189">Aggiornare il pacchetto `Microsoft.Quantum.IQSharp`:</span><span class="sxs-lookup"><span data-stu-id="75577-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="75577-190">Verificare la versione di `iqsharp`:</span><span class="sxs-lookup"><span data-stu-id="75577-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="75577-191">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="75577-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20070124
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="75577-192">Non importa se la versione di `iqsharp` in uso è superiore.</span><span class="sxs-lookup"><span data-stu-id="75577-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="75577-193">Deve corrispondere all'[ultima versione](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="75577-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="75577-194">Eseguire il comando seguente da una cella in ogni notebook di Jupyter Q# esistente:</span><span class="sxs-lookup"><span data-stu-id="75577-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

***

<span data-ttu-id="75577-195">È ora possibile usare il kernel IQ# aggiornato per eseguire i notebook Jupyter Q# esistenti.</span><span class="sxs-lookup"><span data-stu-id="75577-195">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="75577-196">Aggiornare l'estensione Visual Studio QDK</span><span class="sxs-lookup"><span data-stu-id="75577-196">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="75577-197">Aggiornare l'estensione di Visual Studio per Q#</span><span class="sxs-lookup"><span data-stu-id="75577-197">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="75577-198">Visual Studio richiede di accettare gli aggiornamenti all'estensione [Microsoft Quantum Development Kit](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="75577-198">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="75577-199">Accettare l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="75577-199">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="75577-200">I modelli di progetto vengono aggiornati con l'estensione.</span><span class="sxs-lookup"><span data-stu-id="75577-200">The project templates are updated with the extension.</span></span> <span data-ttu-id="75577-201">I modelli aggiornati si applicano solo ai progetti appena creati.</span><span class="sxs-lookup"><span data-stu-id="75577-201">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="75577-202">Il codice per i progetti esistenti non viene aggiornato quando si aggiorna l'estensione.</span><span class="sxs-lookup"><span data-stu-id="75577-202">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="75577-203">Aggiornare l'estensione VS Code QDK</span><span class="sxs-lookup"><span data-stu-id="75577-203">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="75577-204">Aggiornare l'estensione VS Code per il calcolo quantistico</span><span class="sxs-lookup"><span data-stu-id="75577-204">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="75577-205">Riavviare VS Code</span><span class="sxs-lookup"><span data-stu-id="75577-205">Restart VS Code</span></span>
    - <span data-ttu-id="75577-206">Passare alla scheda **Estensioni**</span><span class="sxs-lookup"><span data-stu-id="75577-206">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="75577-207">Selezionare l'estensione **Microsoft Quantum Development Kit for Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="75577-207">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="75577-208">Ricaricare l'estensione</span><span class="sxs-lookup"><span data-stu-id="75577-208">Reload the extension</span></span>

2. <span data-ttu-id="75577-209">Aggiornare i modelli di progetto di calcolo quantistico:</span><span class="sxs-lookup"><span data-stu-id="75577-209">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="75577-210">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="75577-210">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="75577-211">Selezionare **Q#: Installa modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="75577-211">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="75577-212">Dopo alcuni secondi dovrebbe essere visualizzata una finestra popup che conferma la corretta installazione dei modelli di progetto</span><span class="sxs-lookup"><span data-stu-id="75577-212">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="75577-213">C#, con lo strumento da riga di comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="75577-213">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="75577-214">Aggiornare i modelli di progetto di calcolo quantistico per .NET</span><span class="sxs-lookup"><span data-stu-id="75577-214">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
