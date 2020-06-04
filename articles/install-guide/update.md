---
title: Aggiornare Quantum Development Kit (QDK)
description: 'Viene descritto come aggiornare i progetti Q # e i Microsoft Quantum Development Kit alla versione corrente.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 3245f587493ce12cfec15c8f932fd092d85f688e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327570"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="826fb-103">Aggiornare il Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="826fb-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="826fb-104">Informazioni su come aggiornare la Microsoft Quantum Development Kit (QDK) alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="826fb-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="826fb-105">In questo articolo si presuppone che QDK sia già installato.</span><span class="sxs-lookup"><span data-stu-id="826fb-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="826fb-106">Se si sta installando per la prima volta, consultare la Guida all' [installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="826fb-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="826fb-107">Si consiglia di tenersi aggiornati con la versione più recente di QDK.</span><span class="sxs-lookup"><span data-stu-id="826fb-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="826fb-108">Seguire questa guida di aggiornamento per eseguire l'aggiornamento alla versione più recente di QDK.</span><span class="sxs-lookup"><span data-stu-id="826fb-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="826fb-109">Il processo è costituito da due parti:</span><span class="sxs-lookup"><span data-stu-id="826fb-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="826fb-110">Aggiornamento dei file e dei progetti Q # esistenti per allineare il codice con qualsiasi sintassi aggiornata.</span><span class="sxs-lookup"><span data-stu-id="826fb-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="826fb-111">Aggiornamento del QDK stesso per l'ambiente di sviluppo scelto.</span><span class="sxs-lookup"><span data-stu-id="826fb-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="826fb-112">Aggiornamento di progetti Q #</span><span class="sxs-lookup"><span data-stu-id="826fb-112">Updating Q# Projects</span></span> 

<span data-ttu-id="826fb-113">Indipendentemente dal fatto che si usi C# o Python per ospitare le operazioni Q #, seguire queste istruzioni per aggiornare i progetti Q #.</span><span class="sxs-lookup"><span data-stu-id="826fb-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="826fb-114">Per prima cosa, verificare di avere la versione più recente di [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="826fb-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="826fb-115">Eseguire il comando seguente nel prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="826fb-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="826fb-116">Verificare che l'output sia `3.1.100` o superiore.</span><span class="sxs-lookup"><span data-stu-id="826fb-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="826fb-117">In caso contrario, installare la [versione più recente](https://dotnet.microsoft.com/download) e verificare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="826fb-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="826fb-118">Seguire quindi le istruzioni riportate di seguito, a seconda della configurazione (Visual Studio, Visual Studio Code o direttamente dalla riga di comando).</span><span class="sxs-lookup"><span data-stu-id="826fb-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="826fb-119">Aggiornare i progetti Q # in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="826fb-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="826fb-120">Eseguire l'aggiornamento alla versione più recente di Visual Studio 2019. per istruzioni, vedere [qui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) .</span><span class="sxs-lookup"><span data-stu-id="826fb-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="826fb-121">Aprire la soluzione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="826fb-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="826fb-122">Dal menu selezionare **Compila**  ->  **soluzione pulita**.</span><span class="sxs-lookup"><span data-stu-id="826fb-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="826fb-123">In ognuno dei file con estensione csproj aggiornare il Framework di destinazione a `netcoreapp3.1` (o `netstandard2.1` se si tratta di un progetto di libreria).</span><span class="sxs-lookup"><span data-stu-id="826fb-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="826fb-124">Ovvero modificare le righe nel formato:</span><span class="sxs-lookup"><span data-stu-id="826fb-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="826fb-125">Per ulteriori informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="826fb-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="826fb-126">In ognuno dei file con estensione csproj impostare SDK su `Microsoft.Quantum.Sdk` , come indicato nella riga seguente.</span><span class="sxs-lookup"><span data-stu-id="826fb-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="826fb-127">Si noti che il numero di versione deve essere l'ultimo disponibile ed è possibile determinarlo esaminando le note sulla [versione](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="826fb-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="826fb-128">Salvare e chiudere tutti i file nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="826fb-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="826fb-129">Selezionare **strumenti**  ->  **prompt dei comandi per gli sviluppatori riga di comando**  ->  **Developer Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="826fb-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="826fb-130">In alternativa, è possibile usare la console di gestione pacchetti in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="826fb-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="826fb-131">Per ogni progetto nella soluzione, eseguire il comando seguente per **rimuovere** il pacchetto:</span><span class="sxs-lookup"><span data-stu-id="826fb-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="826fb-132">Se i progetti usano qualsiasi altro pacchetto Microsoft. Quantum o Microsoft. Azure. Quantum (ad esempio, Microsoft. Quantum. Numerics), eseguire il comando **Add** per aggiornare la versione usata.</span><span class="sxs-lookup"><span data-stu-id="826fb-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="826fb-133">Chiudere il prompt dei comandi e selezionare **Compila**  ->  **compilazione soluzione** ( *non* selezionare Ricompila soluzione).</span><span class="sxs-lookup"><span data-stu-id="826fb-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="826fb-134">È ora possibile ignorare [l'aggiornamento dell'estensione QDK di Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="826fb-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="826fb-135">Aggiornare i progetti Q # in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="826fb-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="826fb-136">In Visual Studio Code aprire la cartella contenente il progetto da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="826fb-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="826fb-137">Selezionare **terminale**  ->  **nuovo terminale**.</span><span class="sxs-lookup"><span data-stu-id="826fb-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="826fb-138">Seguire le istruzioni per l'aggiornamento usando la riga di comando (direttamente di seguito).</span><span class="sxs-lookup"><span data-stu-id="826fb-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="826fb-139">Aggiornare i progetti Q # usando la riga di comando</span><span class="sxs-lookup"><span data-stu-id="826fb-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="826fb-140">Passare alla cartella contenente il file di progetto principale.</span><span class="sxs-lookup"><span data-stu-id="826fb-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="826fb-141">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="826fb-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="826fb-142">Determinare la versione corrente di QDK.</span><span class="sxs-lookup"><span data-stu-id="826fb-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="826fb-143">Per trovarlo, è possibile esaminare le [Note sulla versione](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="826fb-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="826fb-144">La versione avrà un formato simile a `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="826fb-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="826fb-145">In ogni `.csproj` file seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="826fb-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="826fb-146">Aggiornare il Framework di destinazione a `netcoreapp3.1` (o `netstandard2.1` se si tratta di un progetto di libreria).</span><span class="sxs-lookup"><span data-stu-id="826fb-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="826fb-147">Ovvero modificare le righe nel formato:</span><span class="sxs-lookup"><span data-stu-id="826fb-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="826fb-148">Per ulteriori informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="826fb-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="826fb-149">Sostituire il riferimento all'SDK nella definizione del progetto.</span><span class="sxs-lookup"><span data-stu-id="826fb-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="826fb-150">Verificare che il numero di versione corrisponda al valore determinato nel **passaggio 3**.</span><span class="sxs-lookup"><span data-stu-id="826fb-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="826fb-151">Rimuovere il riferimento al pacchetto `Microsoft.Quantum.Development.Kit` , se presente, che verrà specificato nella voce seguente:</span><span class="sxs-lookup"><span data-stu-id="826fb-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="826fb-152">Aggiornare la versione di tutti i pacchetti Quantum Microsoft alla versione rilasciata più di recente di QDK (determinata nel **passaggio 3**).</span><span class="sxs-lookup"><span data-stu-id="826fb-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="826fb-153">Questi pacchetti vengono denominati con i modelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="826fb-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="826fb-154">I riferimenti ai pacchetti hanno il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="826fb-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="826fb-155">Salvare il file aggiornato.</span><span class="sxs-lookup"><span data-stu-id="826fb-155">Save the updated file.</span></span>

    - <span data-ttu-id="826fb-156">Ripristinare le dipendenze del progetto eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="826fb-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="826fb-157">Tornare alla cartella che contiene il progetto principale ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="826fb-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="826fb-158">Con i progetti Q # ora aggiornati, seguire le istruzioni riportate di seguito per aggiornare il QDK stesso.</span><span class="sxs-lookup"><span data-stu-id="826fb-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="826fb-159">Aggiornamento di QDK</span><span class="sxs-lookup"><span data-stu-id="826fb-159">Updating the QDK</span></span>

<span data-ttu-id="826fb-160">Il processo di aggiornamento del QDK varia a seconda del linguaggio di sviluppo e dell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="826fb-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="826fb-161">Selezionare l'ambiente di sviluppo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="826fb-161">Select your development environment below.</span></span>

* [<span data-ttu-id="826fb-162">Python: aggiornare l'estensione IQ #</span><span class="sxs-lookup"><span data-stu-id="826fb-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="826fb-163">Notebook di Jupyter: aggiornare l'estensione IQ #</span><span class="sxs-lookup"><span data-stu-id="826fb-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="826fb-164">Visual Studio: aggiornare l'estensione QDK</span><span class="sxs-lookup"><span data-stu-id="826fb-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="826fb-165">VS Code: aggiornare l'estensione QDK</span><span class="sxs-lookup"><span data-stu-id="826fb-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="826fb-166">Riga di comando e C#: aggiornare i modelli di progetto</span><span class="sxs-lookup"><span data-stu-id="826fb-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="826fb-167">Aggiornare IQ # per Python</span><span class="sxs-lookup"><span data-stu-id="826fb-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="826fb-168">Aggiornare il `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="826fb-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="826fb-169">Verificare la `iqsharp` versione</span><span class="sxs-lookup"><span data-stu-id="826fb-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="826fb-170">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="826fb-170">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="826fb-171">Non preoccuparti se la tua `iqsharp` versione è più alta, deve corrispondere alla versione [più recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="826fb-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="826fb-172">Aggiornare il `qsharp` pacchetto</span><span class="sxs-lookup"><span data-stu-id="826fb-172">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="826fb-173">Verificare la `qsharp` versione</span><span class="sxs-lookup"><span data-stu-id="826fb-173">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="826fb-174">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="826fb-174">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="826fb-175">Eseguire il comando seguente dal percorso dei `.qs` file</span><span class="sxs-lookup"><span data-stu-id="826fb-175">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="826fb-176">È ora possibile usare la versione aggiornata di QDK per eseguire i programmi Quantum esistenti.</span><span class="sxs-lookup"><span data-stu-id="826fb-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="826fb-177">Aggiornare IQ # per i notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="826fb-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="826fb-178">Aggiornare il `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="826fb-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="826fb-179">Verificare la `iqsharp` versione</span><span class="sxs-lookup"><span data-stu-id="826fb-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="826fb-180">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="826fb-180">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="826fb-181">Non preoccuparti se la tua `iqsharp` versione è più alta, deve corrispondere alla versione [più recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="826fb-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="826fb-182">Eseguire il comando seguente da una cella nel Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="826fb-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="826fb-183">È ora possibile aprire un notebook di Jupyter esistente ed eseguirlo con il QDK aggiornato.</span><span class="sxs-lookup"><span data-stu-id="826fb-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="826fb-184">Aggiorna l'estensione QDK di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="826fb-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="826fb-185">Aggiornare l'estensione di Visual Studio Q #</span><span class="sxs-lookup"><span data-stu-id="826fb-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="826fb-186">Visual Studio richiede di accettare gli aggiornamenti all' [estensione Quantum di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="826fb-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="826fb-187">Accetta l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="826fb-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="826fb-188">I modelli di progetto vengono aggiornati con l'estensione.</span><span class="sxs-lookup"><span data-stu-id="826fb-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="826fb-189">I modelli aggiornati si applicano solo ai progetti appena creati.</span><span class="sxs-lookup"><span data-stu-id="826fb-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="826fb-190">Il codice per i progetti esistenti non viene aggiornato quando viene aggiornata l'estensione.</span><span class="sxs-lookup"><span data-stu-id="826fb-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="826fb-191">Aggiornare VS Code estensione QDK</span><span class="sxs-lookup"><span data-stu-id="826fb-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="826fb-192">Aggiornare l'estensione VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="826fb-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="826fb-193">Riavvia VS Code</span><span class="sxs-lookup"><span data-stu-id="826fb-193">Restart VS Code</span></span>
    - <span data-ttu-id="826fb-194">Passare alla scheda **estensioni**</span><span class="sxs-lookup"><span data-stu-id="826fb-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="826fb-195">Selezionare l' **Microsoft Quantum Development Kit per Visual Studio Code** estensione</span><span class="sxs-lookup"><span data-stu-id="826fb-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="826fb-196">Ricarica l'estensione</span><span class="sxs-lookup"><span data-stu-id="826fb-196">Reload the extension</span></span>

2. <span data-ttu-id="826fb-197">Aggiornare i modelli di progetto Quantum:</span><span class="sxs-lookup"><span data-stu-id="826fb-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="826fb-198">Vai a **Visualizza**  ->  **riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="826fb-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="826fb-199">Selezionare **Q #: installare i modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="826fb-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="826fb-200">Dopo alcuni secondi dovrebbe essere visualizzata una finestra popup che conferma la corretta installazione di modelli di progetto</span><span class="sxs-lookup"><span data-stu-id="826fb-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="826fb-201">C#, uso dello `dotnet` strumento da riga di comando</span><span class="sxs-lookup"><span data-stu-id="826fb-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="826fb-202">Aggiornare i modelli di progetto Quantum per .NET</span><span class="sxs-lookup"><span data-stu-id="826fb-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
