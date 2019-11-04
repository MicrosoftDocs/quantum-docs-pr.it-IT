---
title: Informazioni su come aggiornare il Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185852"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="a3649-102">Aggiornare il Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="a3649-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="a3649-103">Informazioni su come aggiornare la Microsoft Quantum Development Kit (QDK) alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="a3649-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="a3649-104">In questo articolo si presuppone che QDK sia già installato.</span><span class="sxs-lookup"><span data-stu-id="a3649-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="a3649-105">Se si sta installando per la prima volta, consultare la Guida all' [installazione](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="a3649-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="a3649-106">I passaggi di aggiornamento dipendono dall'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="a3649-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="a3649-107">Scegliere l'ambiente nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a3649-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="a3649-108">Python</span><span class="sxs-lookup"><span data-stu-id="a3649-108">Python</span></span>

1. <span data-ttu-id="a3649-109">Aggiornare il kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="a3649-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="a3649-110">Verificare la versione di `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="a3649-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="a3649-111">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="a3649-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="a3649-112">Aggiornare il pacchetto di `qsharp`</span><span class="sxs-lookup"><span data-stu-id="a3649-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="a3649-113">Verificare la versione di `qsharp`</span><span class="sxs-lookup"><span data-stu-id="a3649-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="a3649-114">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="a3649-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="a3649-115">È ora possibile usare la versione aggiornata di QDK per eseguire i programmi Quantum esistenti.</span><span class="sxs-lookup"><span data-stu-id="a3649-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="a3649-116">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="a3649-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="a3649-117">Aggiornare il kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="a3649-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="a3649-118">Verificare la versione di `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="a3649-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="a3649-119">Dovrebbe venire visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="a3649-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="a3649-120">È ora possibile aprire un notebook di Jupyter esistente ed eseguirlo con il QDK aggiornato.</span><span class="sxs-lookup"><span data-stu-id="a3649-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="a3649-121">C#in Windows con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a3649-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="a3649-122">Aggiornare l'estensione di Visual Studio Q #</span><span class="sxs-lookup"><span data-stu-id="a3649-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="a3649-123">Visual Studio richiede di accettare gli aggiornamenti all' [estensione Quantum di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="a3649-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="a3649-124">Accetta l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="a3649-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3649-125">I modelli di progetto vengono aggiornati con l'estensione.</span><span class="sxs-lookup"><span data-stu-id="a3649-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="a3649-126">I modelli aggiornati si applicano solo ai progetti appena creati.</span><span class="sxs-lookup"><span data-stu-id="a3649-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="a3649-127">Il codice per i progetti esistenti non viene aggiornato quando viene aggiornata l'estensione.</span><span class="sxs-lookup"><span data-stu-id="a3649-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="a3649-128">Aggiornare i pacchetti QDK</span><span class="sxs-lookup"><span data-stu-id="a3649-128">Update the QDK packages</span></span>

    - <span data-ttu-id="a3649-129">Apri un'applicazione esistente</span><span class="sxs-lookup"><span data-stu-id="a3649-129">Open an existing application</span></span>
    - <span data-ttu-id="a3649-130">Selezionare le **dipendenze** nella Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="a3649-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="a3649-131">Selezionare **Gestisci pacchetti NuGet**</span><span class="sxs-lookup"><span data-stu-id="a3649-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="a3649-132">Aggiornare i pacchetti **Microsoft. Quantum** alla versione più recente</span><span class="sxs-lookup"><span data-stu-id="a3649-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="a3649-133">È ora possibile eseguire l'applicazione con la versione più recente di QDK.</span><span class="sxs-lookup"><span data-stu-id="a3649-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="a3649-134">C#, utilizzo di VS Code</span><span class="sxs-lookup"><span data-stu-id="a3649-134">C#, using VS Code</span></span>

1. <span data-ttu-id="a3649-135">Aggiornare l'estensione VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="a3649-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="a3649-136">Riavvia VS Code</span><span class="sxs-lookup"><span data-stu-id="a3649-136">Restart VS Code</span></span>
    - <span data-ttu-id="a3649-137">Passare alla scheda **estensioni**</span><span class="sxs-lookup"><span data-stu-id="a3649-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="a3649-138">Selezionare l' **Microsoft Quantum Development Kit per Visual Studio Code** estensione</span><span class="sxs-lookup"><span data-stu-id="a3649-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="a3649-139">Ricarica l'estensione</span><span class="sxs-lookup"><span data-stu-id="a3649-139">Reload the extension</span></span>

1. <span data-ttu-id="a3649-140">Aggiornare i modelli di progetto Quantum:</span><span class="sxs-lookup"><span data-stu-id="a3649-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="a3649-141">Vai a **visualizza** -> **riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="a3649-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="a3649-142">Selezionare **Q #: installare i modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="a3649-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="a3649-143">Aprire un'applicazione esistente in VS Code</span><span class="sxs-lookup"><span data-stu-id="a3649-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="a3649-144">Modificare il file con estensione csproj per aggiungere le nuove versioni del pacchetto</span><span class="sxs-lookup"><span data-stu-id="a3649-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="a3649-145">Se si usano altri pacchetti `Microsoft.Quantum`, aggiornarli.</span><span class="sxs-lookup"><span data-stu-id="a3649-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="a3649-146">È ora possibile eseguire l'applicazione con la QDK aggiornata</span><span class="sxs-lookup"><span data-stu-id="a3649-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="a3649-147">C#, uso dello strumento da riga di comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="a3649-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="a3649-148">Aggiornare i modelli di progetto Quantum per .NET</span><span class="sxs-lookup"><span data-stu-id="a3649-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="a3649-149">Aggiornare ed eseguire un'applicazione esistente</span><span class="sxs-lookup"><span data-stu-id="a3649-149">Update and run an existing application</span></span>

    - <span data-ttu-id="a3649-150">Aggiornare le versioni del pacchetto QDK nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a3649-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="a3649-151">Se l'applicazione usa altri pacchetti di `Microsoft.Quantum`, aggiornarli.</span><span class="sxs-lookup"><span data-stu-id="a3649-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="a3649-152">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="a3649-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="a3649-153">L'applicazione viene eseguita con le nuove versioni del pacchetto</span><span class="sxs-lookup"><span data-stu-id="a3649-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="a3649-154">Potrai anche</span><span class="sxs-lookup"><span data-stu-id="a3649-154">What's next?</span></span>

<span data-ttu-id="a3649-155">Ora che è stato aggiornato Quantum Development Kit nell'ambiente preferito, è possibile continuare a sviluppare ed eseguire i programmi Quantum.</span><span class="sxs-lookup"><span data-stu-id="a3649-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="a3649-156">Se non è ancora stato scritto un programma, è possibile iniziare a usare [il primo programma Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="a3649-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
