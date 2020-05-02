---
title: 'Eseguire programmi Q # senza un driver e una lingua host'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706802"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="b7452-102">Domande della riga di comando Q #</span><span class="sxs-lookup"><span data-stu-id="b7452-102">Q# Command Line Applications</span></span>

<span data-ttu-id="b7452-103">I programmi Q # possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F # o Python.</span><span class="sxs-lookup"><span data-stu-id="b7452-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="b7452-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b7452-104">Pre-requisites</span></span>

- [<span data-ttu-id="b7452-105">.NET Core SDK 3,1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="b7452-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="b7452-106">Installazione</span><span class="sxs-lookup"><span data-stu-id="b7452-106">Installation</span></span>

<span data-ttu-id="b7452-107">Sebbene sia possibile compilare applicazioni della riga di comando di Q # in qualsiasi IDE, si consiglia vivamente di usare Visual Studio Code (VS Code) o l'IDE di Visual Studio per le applicazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="b7452-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="b7452-108">Utilizzando VS Code o Visual Studio e l'estensione di Visual Studio Code QDK è possibile accedere a funzionalità più avanzate.</span><span class="sxs-lookup"><span data-stu-id="b7452-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="b7452-109">Installare [vs code](https://code.visualstudio.com/download) (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="b7452-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="b7452-110">Installare l' [estensione QDK per vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) o</span><span class="sxs-lookup"><span data-stu-id="b7452-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="b7452-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato</span><span class="sxs-lookup"><span data-stu-id="b7452-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="b7452-112">Scaricare e installare l' [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="b7452-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="b7452-113">Sviluppare con Q # usando VS Code</span><span class="sxs-lookup"><span data-stu-id="b7452-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="b7452-114">Installare i modelli di progetto di calcolo quantistico:</span><span class="sxs-lookup"><span data-stu-id="b7452-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="b7452-115">Vai a **Visualizza** -> **riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="b7452-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="b7452-116">Selezionare **Q #: installare i modelli di progetto**</span><span class="sxs-lookup"><span data-stu-id="b7452-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="b7452-117">Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="b7452-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="b7452-118">Creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="b7452-118">Create a new project:</span></span>
  - <span data-ttu-id="b7452-119">Vai a **Visualizza** -> **riquadro comandi**</span><span class="sxs-lookup"><span data-stu-id="b7452-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="b7452-120">Selezionare **Q #: Crea nuovo progetto**</span><span class="sxs-lookup"><span data-stu-id="b7452-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="b7452-121">Seleziona **applicazione console autonoma**</span><span class="sxs-lookup"><span data-stu-id="b7452-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="b7452-122">Passare al percorso del file system in cui si vuole creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="b7452-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="b7452-123">Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**</span><span class="sxs-lookup"><span data-stu-id="b7452-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="b7452-124">Esaminare il progetto</span><span class="sxs-lookup"><span data-stu-id="b7452-124">Inspect the project</span></span>
  - <span data-ttu-id="b7452-125">Dovrebbe essere visualizzato un file denominato `Program.qs` created, ovvero un programma Q # che definisce una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="b7452-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="b7452-126">Eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="b7452-126">Run the application:</span></span>
  - <span data-ttu-id="b7452-127">Vai a **Terminal** -> **New Terminal**</span><span class="sxs-lookup"><span data-stu-id="b7452-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="b7452-128">Immettere `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="b7452-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="b7452-129">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b7452-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="b7452-130">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b7452-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="b7452-131">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="b7452-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="b7452-132">Sviluppare con Q # con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b7452-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="b7452-133">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="b7452-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="b7452-134">Creare una nuova applicazione Q#</span><span class="sxs-lookup"><span data-stu-id="b7452-134">Create a new Q# application</span></span>
  - <span data-ttu-id="b7452-135">Vai a **file** -> **nuovo** -> **progetto**</span><span class="sxs-lookup"><span data-stu-id="b7452-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="b7452-136">Digitare `Q#` nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="b7452-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="b7452-137">Selezionare **Applicazione Q#**</span><span class="sxs-lookup"><span data-stu-id="b7452-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="b7452-138">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b7452-138">Select **Next**</span></span>
  - <span data-ttu-id="b7452-139">Scegliere un nome e una posizione per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="b7452-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="b7452-140">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="b7452-140">Select **Create**</span></span>

- <span data-ttu-id="b7452-141">Esaminare il progetto</span><span class="sxs-lookup"><span data-stu-id="b7452-141">Inspect the project</span></span>
  - <span data-ttu-id="b7452-142">Si noterà che è stato creato un `Program.qs` file denominato, ovvero un programma Q # che definisce una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="b7452-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="b7452-143">Eseguire l'applicazione</span><span class="sxs-lookup"><span data-stu-id="b7452-143">Run the application</span></span>
  - <span data-ttu-id="b7452-144">Selezionare **debug** -> **Avvia senza eseguire debug**</span><span class="sxs-lookup"><span data-stu-id="b7452-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="b7452-145">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="b7452-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="b7452-146">Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="b7452-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="b7452-147">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="b7452-147">What's next?</span></span>

<span data-ttu-id="b7452-148">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="b7452-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
