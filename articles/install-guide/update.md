---
title: Aggiornare Quantum Development Kit (QDK)
description: 'Viene descritto come aggiornare i progetti Q # e i Microsoft Quantum Development Kit alla versione corrente.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 53f72f1d49ae32a5a8572a1cf68a66a1d9b45e4a
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426900"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="13cff-103">Aggiornare il Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="13cff-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="13cff-104">Informazioni su come aggiornare la Microsoft Quantum Development Kit (QDK) alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="13cff-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="13cff-105">In questo articolo si presuppone che QDK sia già installato.</span><span class="sxs-lookup"><span data-stu-id="13cff-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="13cff-106">Se si sta installando per la prima volta, consultare la Guida all' [installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="13cff-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="13cff-107">Si consiglia di tenersi aggiornati con la versione più recente di QDK.</span><span class="sxs-lookup"><span data-stu-id="13cff-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="13cff-108">Seguire questa guida di aggiornamento per eseguire l'aggiornamento alla versione più recente di QDK.</span><span class="sxs-lookup"><span data-stu-id="13cff-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="13cff-109">Il processo è costituito da due parti:</span><span class="sxs-lookup"><span data-stu-id="13cff-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="13cff-110">aggiornamento dei file e dei progetti Q # esistenti per allineare il codice con qualsiasi sintassi aggiornata</span><span class="sxs-lookup"><span data-stu-id="13cff-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="13cff-111">aggiornamento del QDK stesso per l'ambiente di sviluppo scelto</span><span class="sxs-lookup"><span data-stu-id="13cff-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="13cff-112">Aggiornamento di progetti Q #</span><span class="sxs-lookup"><span data-stu-id="13cff-112">Updating Q# Projects</span></span> 

<span data-ttu-id="13cff-113">Indipendentemente dal fatto che si usi C# o Python per ospitare le operazioni Q #, seguire queste istruzioni per aggiornare i progetti Q #.</span><span class="sxs-lookup"><span data-stu-id="13cff-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="13cff-114">Per prima cosa, verificare di avere la versione più recente di [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="13cff-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="13cff-115">Eseguire il comando seguente nel prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="13cff-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="13cff-116">Verificare che l'output sia `3.1.100` o superiore.</span><span class="sxs-lookup"><span data-stu-id="13cff-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="13cff-117">In caso contrario, installare la [versione più recente](https://dotnet.microsoft.com/download) e verificare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="13cff-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="13cff-118">Seguire quindi le istruzioni riportate di seguito, a seconda della configurazione (Visual Studio, Visual Studio Code o direttamente dalla riga di comando).</span><span class="sxs-lookup"><span data-stu-id="13cff-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="13cff-119">Aggiornare i progetti Q # in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="13cff-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="13cff-120">Eseguire l'aggiornamento alla versione più recente di Visual Studio 2019, vedere [qui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) per istruzioni</span><span class="sxs-lookup"><span data-stu-id="13cff-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="13cff-121">Aprire la soluzione in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="13cff-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="13cff-122">Dal menu selezionare **Compila**  ->  **soluzione pulita**</span><span class="sxs-lookup"><span data-stu-id="13cff-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="13cff-123">In ognuno dei file con estensione csproj aggiornare il Framework di destinazione a `netcoreapp3.1` (o `netstandard2.1` se si tratta di un progetto di libreria).</span><span class="sxs-lookup"><span data-stu-id="13cff-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="13cff-124">Ovvero modificare le righe nel formato:</span><span class="sxs-lookup"><span data-stu-id="13cff-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="13cff-125">Per ulteriori informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="13cff-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="13cff-126">Salvare e chiudere tutti i file nella soluzione</span><span class="sxs-lookup"><span data-stu-id="13cff-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="13cff-127">Selezionare **strumenti**dalla  ->  **riga di comando**  ->  **prompt dei comandi per gli sviluppatori**</span><span class="sxs-lookup"><span data-stu-id="13cff-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="13cff-128">Per ogni progetto nella soluzione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13cff-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="13cff-129">Se i progetti usano qualsiasi altro pacchetto Microsoft. Quantum (ad esempio, Microsoft. Quantum. Numerics), eseguire il comando anche per questi.</span><span class="sxs-lookup"><span data-stu-id="13cff-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="13cff-130">Chiudere il prompt dei comandi e selezionare **Compila**  ->  **Compila soluzione** ( *non* selezionare Ricompila soluzione)</span><span class="sxs-lookup"><span data-stu-id="13cff-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="13cff-131">È ora possibile ignorare [l'aggiornamento dell'estensione QDK di Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="13cff-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="13cff-132">Aggiornare i progetti Q # in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="13cff-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="13cff-133">In Visual Studio Code aprire la cartella contenente il progetto da aggiornare</span><span class="sxs-lookup"><span data-stu-id="13cff-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="13cff-134">Selezionare **terminale**  ->  **nuovo terminale**</span><span class="sxs-lookup"><span data-stu-id="13cff-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="13cff-135">Seguire le istruzioni per l'aggiornamento usando la riga di comando (direttamente di seguito)</span><span class="sxs-lookup"><span data-stu-id="13cff-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="13cff-136">Aggiornare i progetti Q # usando la riga di comando</span><span class="sxs-lookup"><span data-stu-id="13cff-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="13cff-137">Passare alla cartella contenente il file di progetto</span><span class="sxs-lookup"><span data-stu-id="13cff-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="13cff-138">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13cff-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="13cff-139">In ognuno dei file con estensione csproj aggiornare il Framework di destinazione a `netcoreapp3.1` (o `netstandard2.1` se si tratta di un progetto di libreria).</span><span class="sxs-lookup"><span data-stu-id="13cff-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="13cff-140">Ovvero modificare le righe nel formato:</span><span class="sxs-lookup"><span data-stu-id="13cff-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="13cff-141">Per ulteriori informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="13cff-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="13cff-142">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="13cff-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="13cff-143">Se il progetto usa altri pacchetti Microsoft. Quantum (ad esempio, Microsoft. Quantum. Numerics), eseguire il comando anche per questi.</span><span class="sxs-lookup"><span data-stu-id="13cff-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="13cff-144">Salvare e chiudere tutti i file.</span><span class="sxs-lookup"><span data-stu-id="13cff-144">Save and close all files.</span></span>
6. <span data-ttu-id="13cff-145">Ripetere 1-4 per ogni dipendenza del progetto, quindi tornare alla cartella che contiene il progetto principale ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="13cff-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="13cff-146">Con i progetti Q # ora aggiornati, seguire le istruzioni riportate di seguito per aggiornare il QDK stesso.</span><span class="sxs-lookup"><span data-stu-id="13cff-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="13cff-147">Aggiornamento di QDK</span><span class="sxs-lookup"><span data-stu-id="13cff-147">Updating the QDK</span></span>

<span data-ttu-id="13cff-148">Il processo di aggiornamento del QDK varia a seconda del linguaggio di sviluppo e dell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="13cff-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="13cff-149">Selezionare l'ambiente di sviluppo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="13cff-149">Select your development environment below.</span></span>

* [<span data-ttu-id="13cff-150">Python: aggiornare l'estensione IQ #</span><span class="sxs-lookup"><span data-stu-id="13cff-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="13cff-151">Notebook di Jupyter: aggiornare l'estensione IQ #</span><span class="sxs-lookup"><span data-stu-id="13cff-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="13cff-152">Visual Studio: aggiornare l'estensione QDK</span><span class="sxs-lookup"><span data-stu-id="13cff-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="13cff-153">VS Code: aggiornare l'estensione QDK</span><span class="sxs-lookup"><span data-stu-id="13cff-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="13cff-154">Riga di comando e C#: aggiornare i modelli di progetto</span><span class="sxs-lookup"><span data-stu-id="13cff-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="13cff-155">Aggiornare IQ # per Python</span><span class="sxs-lookup"><span data-stu-id="13cff-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="13cff-156">Aggiornare il `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="13cff-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="13cff-157">Verificare la `iqsharp` versione</span><span class="sxs-lookup"><span data-stu-id="13cff-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="13cff-158">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="13cff-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="13cff-159">Non preoccuparti se la tua `iqsharp` versione è più alta, deve corrispondere alla versione [più recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="13cff-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="13cff-160">Aggiornare il `qsharp` pacchetto</span><span class="sxs-lookup"><span data-stu-id="13cff-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="13cff-161">Verificare la `qsharp` versione</span><span class="sxs-lookup"><span data-stu-id="13cff-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="13cff-162">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="13cff-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="13cff-163">Eseguire il comando seguente dal percorso dei `.qs` file</span><span class="sxs-lookup"><span data-stu-id="13cff-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="13cff-164">È ora possibile usare la versione aggiornata di QDK per eseguire i programmi Quantum esistenti.</span><span class="sxs-lookup"><span data-stu-id="13cff-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="13cff-165">Aggiornare IQ # per i notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="13cff-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="13cff-166">Aggiornare il `iqsharp` kernel</span><span class="sxs-lookup"><span data-stu-id="13cff-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="13cff-167">Verificare la `iqsharp` versione</span><span class="sxs-lookup"><span data-stu-id="13cff-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="13cff-168">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="13cff-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="13cff-169">Non preoccuparti se la tua `iqsharp` versione è più alta, deve corrispondere alla versione [più recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="13cff-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="13cff-170">Eseguire il comando seguente da una cella nel Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="13cff-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="13cff-171">È ora possibile aprire un notebook di Jupyter esistente ed eseguirlo con il QDK aggiornato.</span><span class="sxs-lookup"><span data-stu-id="13cff-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="13cff-172">Aggiorna l'estensione QDK di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="13cff-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="13cff-173">Aggiornare l'estensione di Visual Studio Q #</span><span class="sxs-lookup"><span data-stu-id="13cff-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="13cff-174">Visual Studio richiede di accettare gli aggiornamenti all' [estensione Quantum di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="13cff-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="13cff-175">Accetta l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="13cff-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="13cff-176">I modelli di progetto vengono aggiornati con l'estensione.</span><span class="sxs-lookup"><span data-stu-id="13cff-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="13cff-177">I modelli aggiornati si applicano solo ai progetti appena creati.</span><span class="sxs-lookup"><span data-stu-id="13cff-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="13cff-178">Il codice per i progetti esistenti non viene aggiornato quando viene aggiornata l'estensione.</span><span class="sxs-lookup"><span data-stu-id="13cff-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="13cff-179">Aggiornare VS Code estensione QDK</span><span class="sxs-lookup"><span data-stu-id="13cff-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="13cff-180">Aggiornare l'estensione VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="13cff-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="13cff-181">Riavvia VS Code</span><span class="sxs-lookup"><span data-stu-id="13cff-181">Restart VS Code</span></span>
    - <span data-ttu-id="13cff-182">Passare alla scheda **estensioni**</span><span class="sxs-lookup"><span data-stu-id="13cff-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="13cff-183">Selezionare l' **Microsoft Quantum Development Kit per Visual Studio Code** estensione</span><span class="sxs-lookup"><span data-stu-id="13cff-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="13cff-184">Ricarica l'estensione</span><span class="sxs-lookup"><span data-stu-id="13cff-184">Reload the extension</span></span>

2. <span data-ttu-id="13cff-185">Aggiornare i modelli di progetto Quantum:</span><span class="sxs-lookup"><span data-stu-id="13cff-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="13cff-186">Vai a **Visualizza**  ->  **riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="13cff-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="13cff-187">Selezionare **Q #: installare i modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="13cff-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="13cff-188">Dopo alcuni secondi dovrebbe essere visualizzata una finestra popup che conferma la corretta installazione di modelli di progetto</span><span class="sxs-lookup"><span data-stu-id="13cff-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="13cff-189">C#, uso dello `dotnet` strumento da riga di comando</span><span class="sxs-lookup"><span data-stu-id="13cff-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="13cff-190">Aggiornare i modelli di progetto Quantum per .NET</span><span class="sxs-lookup"><span data-stu-id="13cff-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```