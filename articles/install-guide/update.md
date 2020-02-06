---
title: Informazioni su come aggiornare il Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036312"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="b19fd-102">Aggiornare il Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="b19fd-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="b19fd-103">Informazioni su come aggiornare la Microsoft Quantum Development Kit (QDK) alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="b19fd-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="b19fd-104">In questo articolo si presuppone che QDK sia già installato.</span><span class="sxs-lookup"><span data-stu-id="b19fd-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="b19fd-105">Se si sta installando per la prima volta, consultare la Guida all' [installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="b19fd-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b19fd-106">Si consiglia di tenersi aggiornati con la versione più recente di QDK.</span><span class="sxs-lookup"><span data-stu-id="b19fd-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="b19fd-107">Seguire questa guida di aggiornamento per eseguire l'aggiornamento alla versione più recente di QDK.</span><span class="sxs-lookup"><span data-stu-id="b19fd-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="b19fd-108">Il processo è costituito da due parti:</span><span class="sxs-lookup"><span data-stu-id="b19fd-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="b19fd-109">aggiornamento dei file e dei progetti Q # esistenti per allineare il codice con qualsiasi sintassi aggiornata</span><span class="sxs-lookup"><span data-stu-id="b19fd-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="b19fd-110">aggiornamento del QDK stesso per l'ambiente di sviluppo scelto</span><span class="sxs-lookup"><span data-stu-id="b19fd-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="b19fd-111">Aggiornamento di progetti Q #</span><span class="sxs-lookup"><span data-stu-id="b19fd-111">Updating Q# Projects</span></span> 

<span data-ttu-id="b19fd-112">Indipendentemente dal fatto che si usi C# o Python per ospitare le operazioni q #, seguire queste istruzioni per aggiornare i progetti q #.</span><span class="sxs-lookup"><span data-stu-id="b19fd-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="b19fd-113">Per prima cosa, verificare di avere la versione più recente di [.NET Core SDK 3,1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="b19fd-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="b19fd-114">Eseguire il comando seguente nel prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="b19fd-114">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="b19fd-115">Verificare che l'output sia `3.1.100` o superiore.</span><span class="sxs-lookup"><span data-stu-id="b19fd-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="b19fd-116">In caso contrario, installare la [versione più recente](https://dotnet.microsoft.com/download) e verificare di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b19fd-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="b19fd-117">Seguire quindi le istruzioni riportate di seguito, a seconda della configurazione (Visual Studio, Visual Studio Code o direttamente dalla riga di comando).</span><span class="sxs-lookup"><span data-stu-id="b19fd-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="b19fd-118">Aggiornare i progetti Q # in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b19fd-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="b19fd-119">Eseguire l'aggiornamento alla versione più recente di Visual Studio 2019, vedere [qui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) per istruzioni</span><span class="sxs-lookup"><span data-stu-id="b19fd-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="b19fd-120">Aprire la soluzione in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b19fd-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="b19fd-121">Dal menu selezionare **compila** -> **Pulisci soluzione**</span><span class="sxs-lookup"><span data-stu-id="b19fd-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="b19fd-122">In ognuno dei file con estensione csproj aggiornare il Framework di destinazione in modo che `netcoreapp3.0` o `netstandard2.1` se si tratta di un progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="b19fd-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="b19fd-123">Ovvero modificare le righe nel formato:</span><span class="sxs-lookup"><span data-stu-id="b19fd-123">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="b19fd-124">Per ulteriori informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="b19fd-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="b19fd-125">Salvare e chiudere tutti i file nella soluzione</span><span class="sxs-lookup"><span data-stu-id="b19fd-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="b19fd-126">Selezionare **strumenti** -> **riga di comando** -> **prompt dei comandi per gli sviluppatori**</span><span class="sxs-lookup"><span data-stu-id="b19fd-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="b19fd-127">Per ogni progetto nella soluzione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b19fd-127">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="b19fd-128">Se i progetti usano qualsiasi altro pacchetto Microsoft. Quantum (ad esempio, Microsoft. Quantum. Numerics), eseguire il comando anche per questi.</span><span class="sxs-lookup"><span data-stu-id="b19fd-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="b19fd-129">Chiudere il prompt dei comandi e selezionare **compila** -> **Compila soluzione** ( *non* selezionare Ricompila soluzione)</span><span class="sxs-lookup"><span data-stu-id="b19fd-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="b19fd-130">È ora possibile ignorare [l'aggiornamento dell'estensione QDK di Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="b19fd-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="b19fd-131">Aggiornare i progetti Q # in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b19fd-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="b19fd-132">In Visual Studio Code aprire la cartella contenente il progetto da aggiornare</span><span class="sxs-lookup"><span data-stu-id="b19fd-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="b19fd-133">Selezionare **terminal** -> **nuovo terminale**</span><span class="sxs-lookup"><span data-stu-id="b19fd-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="b19fd-134">Seguire le istruzioni per l'aggiornamento usando la riga di comando (direttamente di seguito)</span><span class="sxs-lookup"><span data-stu-id="b19fd-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="b19fd-135">Aggiornare i progetti Q # usando la riga di comando</span><span class="sxs-lookup"><span data-stu-id="b19fd-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="b19fd-136">Passare alla cartella contenente il file di progetto</span><span class="sxs-lookup"><span data-stu-id="b19fd-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="b19fd-137">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b19fd-137">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="b19fd-138">In ognuno dei file con estensione csproj aggiornare il Framework di destinazione in modo che `netcoreapp3.0` o `netstandard2.1` se si tratta di un progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="b19fd-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="b19fd-139">Ovvero modificare le righe nel formato:</span><span class="sxs-lookup"><span data-stu-id="b19fd-139">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="b19fd-140">Per ulteriori informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="b19fd-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="b19fd-141">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b19fd-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="b19fd-142">Se il progetto usa altri pacchetti Microsoft. Quantum (ad esempio, Microsoft. Quantum. Numerics), eseguire il comando anche per questi.</span><span class="sxs-lookup"><span data-stu-id="b19fd-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="b19fd-143">Salvare e chiudere tutti i file.</span><span class="sxs-lookup"><span data-stu-id="b19fd-143">Save and close all files.</span></span>
6. <span data-ttu-id="b19fd-144">Ripetere 1-4 per ogni dipendenza del progetto, quindi tornare alla cartella che contiene il progetto principale ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="b19fd-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="b19fd-145">Con i progetti Q # ora aggiornati, seguire le istruzioni riportate di seguito per aggiornare il QDK stesso.</span><span class="sxs-lookup"><span data-stu-id="b19fd-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="b19fd-146">Aggiornamento di QDK</span><span class="sxs-lookup"><span data-stu-id="b19fd-146">Updating the QDK</span></span>

<span data-ttu-id="b19fd-147">Il processo di aggiornamento del QDK varia a seconda del linguaggio di sviluppo e dell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="b19fd-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="b19fd-148">Selezionare l'ambiente di sviluppo indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b19fd-148">Select your development environment below.</span></span>

* [<span data-ttu-id="b19fd-149">Python: aggiornare l'estensione IQ #</span><span class="sxs-lookup"><span data-stu-id="b19fd-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="b19fd-150">Notebook di Jupyter: aggiornare l'estensione IQ #</span><span class="sxs-lookup"><span data-stu-id="b19fd-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="b19fd-151">Visual Studio: aggiornare l'estensione QDK</span><span class="sxs-lookup"><span data-stu-id="b19fd-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="b19fd-152">VS Code: aggiornare l'estensione QDK</span><span class="sxs-lookup"><span data-stu-id="b19fd-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="b19fd-153">Riga di comando e C#: aggiornare i modelli di progetto</span><span class="sxs-lookup"><span data-stu-id="b19fd-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="b19fd-154">Aggiornare IQ # per Python</span><span class="sxs-lookup"><span data-stu-id="b19fd-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="b19fd-155">Aggiornare il kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="b19fd-155">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="b19fd-156">Verificare la versione di `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="b19fd-156">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="b19fd-157">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="b19fd-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="b19fd-158">Non preoccuparti se la versione del `iqsharp` è superiore, deve corrispondere alla versione [più recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="b19fd-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="b19fd-159">Aggiornare il pacchetto di `qsharp`</span><span class="sxs-lookup"><span data-stu-id="b19fd-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="b19fd-160">Verificare la versione di `qsharp`</span><span class="sxs-lookup"><span data-stu-id="b19fd-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="b19fd-161">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="b19fd-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="b19fd-162">Eseguire il comando seguente dal percorso dei file di `.qs`</span><span class="sxs-lookup"><span data-stu-id="b19fd-162">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="b19fd-163">È ora possibile usare la versione aggiornata di QDK per eseguire i programmi Quantum esistenti.</span><span class="sxs-lookup"><span data-stu-id="b19fd-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="b19fd-164">Aggiornare IQ # per i notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="b19fd-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="b19fd-165">Aggiornare il kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="b19fd-165">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="b19fd-166">Verificare la versione di `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="b19fd-166">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="b19fd-167">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b19fd-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="b19fd-168">Non preoccuparti se la versione del `iqsharp` è superiore, deve corrispondere alla versione [più recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="b19fd-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="b19fd-169">Eseguire il comando seguente da una cella nel Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="b19fd-169">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="b19fd-170">È ora possibile aprire un notebook di Jupyter esistente ed eseguirlo con il QDK aggiornato.</span><span class="sxs-lookup"><span data-stu-id="b19fd-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="b19fd-171">Aggiorna l'estensione QDK di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b19fd-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="b19fd-172">Aggiornare l'estensione di Visual Studio Q #</span><span class="sxs-lookup"><span data-stu-id="b19fd-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="b19fd-173">Visual Studio richiede di accettare gli aggiornamenti all' [estensione Quantum di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="b19fd-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="b19fd-174">Accetta l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="b19fd-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="b19fd-175">I modelli di progetto vengono aggiornati con l'estensione.</span><span class="sxs-lookup"><span data-stu-id="b19fd-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="b19fd-176">I modelli aggiornati si applicano solo ai progetti appena creati.</span><span class="sxs-lookup"><span data-stu-id="b19fd-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="b19fd-177">Il codice per i progetti esistenti non viene aggiornato quando viene aggiornata l'estensione.</span><span class="sxs-lookup"><span data-stu-id="b19fd-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="b19fd-178">Aggiornare VS Code estensione QDK</span><span class="sxs-lookup"><span data-stu-id="b19fd-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="b19fd-179">Aggiornare l'estensione VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="b19fd-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="b19fd-180">Riavvia VS Code</span><span class="sxs-lookup"><span data-stu-id="b19fd-180">Restart VS Code</span></span>
    - <span data-ttu-id="b19fd-181">Passare alla scheda **estensioni**</span><span class="sxs-lookup"><span data-stu-id="b19fd-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="b19fd-182">Selezionare l' **Microsoft Quantum Development Kit per Visual Studio Code** estensione</span><span class="sxs-lookup"><span data-stu-id="b19fd-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="b19fd-183">Ricarica l'estensione</span><span class="sxs-lookup"><span data-stu-id="b19fd-183">Reload the extension</span></span>

2. <span data-ttu-id="b19fd-184">Aggiornare i modelli di progetto Quantum:</span><span class="sxs-lookup"><span data-stu-id="b19fd-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="b19fd-185">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="b19fd-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="b19fd-186">Selezionare **Q #: installare i modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="b19fd-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="b19fd-187">Dopo alcuni secondi dovrebbe essere visualizzata una finestra popup che conferma la corretta installazione di modelli di progetto</span><span class="sxs-lookup"><span data-stu-id="b19fd-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="b19fd-188">C#, uso dello strumento da riga di comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="b19fd-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="b19fd-189">Aggiornare i modelli di progetto Quantum per .NET</span><span class="sxs-lookup"><span data-stu-id="b19fd-189">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="b19fd-190">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="b19fd-190">What's next?</span></span>

<span data-ttu-id="b19fd-191">Ora che è stato aggiornato Quantum Development Kit nell'ambiente preferito, è possibile continuare a sviluppare ed eseguire i programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="b19fd-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="b19fd-192">Se non è ancora stato scritto un programma, è possibile iniziare a usare [il primo programma Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="b19fd-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
