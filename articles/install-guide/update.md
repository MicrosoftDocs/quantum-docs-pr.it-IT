---
title: Informazioni su come aggiornare il Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463290"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="e7832-102">Aggiornare il Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="e7832-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="e7832-103">Informazioni su come aggiornare la Microsoft Quantum Development Kit (QDK) alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="e7832-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="e7832-104">In questo articolo si presuppone che QDK sia già installato.</span><span class="sxs-lookup"><span data-stu-id="e7832-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="e7832-105">Se si sta installando per la prima volta, consultare la Guida all' [installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="e7832-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="e7832-106">Aggiornamento di progetti Q #</span><span class="sxs-lookup"><span data-stu-id="e7832-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="e7832-107">Prima di tutto, installare la versione più recente del [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) ed eseguire il comando seguente nel prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e7832-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="e7832-108">Verificare che l'output sia 3.0.100 o superiore, quindi seguire le istruzioni riportate di seguito in base alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7832-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="e7832-109">In Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7832-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="e7832-110">Eseguire l'aggiornamento alla versione più recente di Visual Studio 2019, vedere [qui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) per istruzioni</span><span class="sxs-lookup"><span data-stu-id="e7832-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="e7832-111">Aprire la soluzione in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7832-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="e7832-112">Dal menu selezionare Compila > Pulisci soluzione</span><span class="sxs-lookup"><span data-stu-id="e7832-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="e7832-113">[Aggiornare il Framework di destinazione](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in ogni file con estensione csproj a netcoreapp 3.0 (o netstandard 2.1 se è un progetto di libreria)</span><span class="sxs-lookup"><span data-stu-id="e7832-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="e7832-114">Salvare e chiudere tutti i file nella soluzione</span><span class="sxs-lookup"><span data-stu-id="e7832-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="e7832-115">Selezionare Strumenti > riga di comando > Prompt dei comandi per gli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="e7832-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="e7832-116">Per ogni progetto nella soluzione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7832-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="e7832-117">Se i progetti usano altri pacchetti Microsoft. Quantum, eseguire il comando anche per questi pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e7832-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="e7832-118">Chiudere il prompt dei comandi e selezionare Compila > Compila soluzione ( *non* selezionare Ricompila soluzione perché la ricompilazione avrà inizialmente esito negativo)</span><span class="sxs-lookup"><span data-stu-id="e7832-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="e7832-119">In Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e7832-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="e7832-120">In Visual Studio Code aprire la cartella contenente il progetto da aggiornare</span><span class="sxs-lookup"><span data-stu-id="e7832-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="e7832-121">Selezionare terminal > nuovo terminale</span><span class="sxs-lookup"><span data-stu-id="e7832-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="e7832-122">Seguire le istruzioni per l'aggiornamento tramite la riga di comando</span><span class="sxs-lookup"><span data-stu-id="e7832-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="e7832-123">Uso della riga di comando</span><span class="sxs-lookup"><span data-stu-id="e7832-123">Using the command line</span></span>

1. <span data-ttu-id="e7832-124">Passare alla cartella contenente il file di progetto</span><span class="sxs-lookup"><span data-stu-id="e7832-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="e7832-125">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7832-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="e7832-126">[Aggiornare il Framework di destinazione](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in ogni file con estensione csproj a netcoreapp 3.0 (o netstandard 2.1 se è un progetto di libreria)</span><span class="sxs-lookup"><span data-stu-id="e7832-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="e7832-127">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7832-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="e7832-128">Se il progetto usa altri pacchetti Microsoft. Quantum, eseguire il comando anche per questi pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e7832-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="e7832-129">Salva e Chiudi tutti i file</span><span class="sxs-lookup"><span data-stu-id="e7832-129">Save and close all files</span></span>
6. <span data-ttu-id="e7832-130">Ripetere 1-4 per ogni dipendenza del progetto, quindi tornare alla cartella che contiene il progetto principale ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="e7832-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="e7832-131">Aggiornare IQ # per Python</span><span class="sxs-lookup"><span data-stu-id="e7832-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="e7832-132">Aggiornare il kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="e7832-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="e7832-133">Verificare la versione di `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="e7832-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="e7832-134">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="e7832-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="e7832-135">Aggiornare il pacchetto di `qsharp`</span><span class="sxs-lookup"><span data-stu-id="e7832-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="e7832-136">Verificare la versione di `qsharp`</span><span class="sxs-lookup"><span data-stu-id="e7832-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="e7832-137">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="e7832-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="e7832-138">Eseguire il comando seguente dal percorso dei file di `.qs`</span><span class="sxs-lookup"><span data-stu-id="e7832-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="e7832-139">È ora possibile usare la versione aggiornata di QDK per eseguire i programmi Quantum esistenti.</span><span class="sxs-lookup"><span data-stu-id="e7832-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="e7832-140">Aggiornare IQ # per i notebook di Jupyter</span><span class="sxs-lookup"><span data-stu-id="e7832-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="e7832-141">Aggiornare il kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="e7832-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="e7832-142">Verificare la versione di `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="e7832-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="e7832-143">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="e7832-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="e7832-144">Eseguire il comando seguente da una cella nel Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="e7832-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="e7832-145">È ora possibile aprire un notebook di Jupyter esistente ed eseguirlo con il QDK aggiornato.</span><span class="sxs-lookup"><span data-stu-id="e7832-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="e7832-146">Aggiorna l'estensione QDK di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e7832-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="e7832-147">Aggiornare l'estensione di Visual Studio Q #</span><span class="sxs-lookup"><span data-stu-id="e7832-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="e7832-148">Visual Studio richiede di accettare gli aggiornamenti all' [estensione Quantum di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="e7832-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="e7832-149">Accetta l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e7832-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7832-150">I modelli di progetto vengono aggiornati con l'estensione.</span><span class="sxs-lookup"><span data-stu-id="e7832-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="e7832-151">I modelli aggiornati si applicano solo ai progetti appena creati.</span><span class="sxs-lookup"><span data-stu-id="e7832-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="e7832-152">Il codice per i progetti esistenti non viene aggiornato quando viene aggiornata l'estensione.</span><span class="sxs-lookup"><span data-stu-id="e7832-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="e7832-153">Aggiornare VS Code estensione QDK</span><span class="sxs-lookup"><span data-stu-id="e7832-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="e7832-154">Aggiornare l'estensione VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="e7832-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="e7832-155">Riavvia VS Code</span><span class="sxs-lookup"><span data-stu-id="e7832-155">Restart VS Code</span></span>
    - <span data-ttu-id="e7832-156">Passare alla scheda **estensioni**</span><span class="sxs-lookup"><span data-stu-id="e7832-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="e7832-157">Selezionare l' **Microsoft Quantum Development Kit per Visual Studio Code** estensione</span><span class="sxs-lookup"><span data-stu-id="e7832-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="e7832-158">Ricarica l'estensione</span><span class="sxs-lookup"><span data-stu-id="e7832-158">Reload the extension</span></span>

1. <span data-ttu-id="e7832-159">Aggiornare i modelli di progetto Quantum:</span><span class="sxs-lookup"><span data-stu-id="e7832-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="e7832-160">Passare a **Visualizza** -> **Riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="e7832-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="e7832-161">Selezionare **Q #: installare i modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="e7832-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="e7832-162">C#, uso dello strumento da riga di comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="e7832-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="e7832-163">Aggiornare i modelli di progetto Quantum per .NET</span><span class="sxs-lookup"><span data-stu-id="e7832-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="e7832-164">Potrai anche</span><span class="sxs-lookup"><span data-stu-id="e7832-164">What's next?</span></span>

<span data-ttu-id="e7832-165">Ora che è stato aggiornato Quantum Development Kit nell'ambiente preferito, è possibile continuare a sviluppare ed eseguire i programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="e7832-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="e7832-166">Se non è ancora stato scritto un programma, è possibile iniziare a usare [il primo programma Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="e7832-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
