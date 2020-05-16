---
title: 'Sviluppare con le applicazioni da riga di comando Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426427"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="92038-102">Sviluppare con le applicazioni da riga di comando Q #</span><span class="sxs-lookup"><span data-stu-id="92038-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="92038-103">I programmi Q # possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F # o Python.</span><span class="sxs-lookup"><span data-stu-id="92038-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="92038-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="92038-104">Pre-requisites</span></span>

- [<span data-ttu-id="92038-105">.NET Core SDK 3,1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="92038-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="92038-106">Installazione</span><span class="sxs-lookup"><span data-stu-id="92038-106">Installation</span></span>

<span data-ttu-id="92038-107">Sebbene sia possibile compilare applicazioni della riga di comando di Q # in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) o IDE di Visual Studio per le applicazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="92038-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="92038-108">Lo sviluppo in questi strumenti consente di accedere a funzionalità avanzate.</span><span class="sxs-lookup"><span data-stu-id="92038-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="92038-109">Per configurare VS Code:</span><span class="sxs-lookup"><span data-stu-id="92038-109">To configure VS Code:</span></span>

1. <span data-ttu-id="92038-110">Scaricare e installare [vs code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="92038-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="92038-111">Installare [Microsoft QDK per vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="92038-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="92038-112">Per configurare Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="92038-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="92038-113">Scaricare e installare [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 o versione successiva con il carico di lavoro sviluppo multipiattaforma .NET Core abilitato.</span><span class="sxs-lookup"><span data-stu-id="92038-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="92038-114">Scaricare e installare [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="92038-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="92038-115">Sviluppare con Q # usando VS Code</span><span class="sxs-lookup"><span data-stu-id="92038-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="92038-116">Installare i modelli di progetto Q #:</span><span class="sxs-lookup"><span data-stu-id="92038-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="92038-117">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="92038-117">Open VS Code.</span></span>
2. <span data-ttu-id="92038-118">Fare clic su **Visualizza**  ->  **riquadro comandi**.</span><span class="sxs-lookup"><span data-stu-id="92038-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="92038-119">Selezionare **Q #: install Project Templates**.</span><span class="sxs-lookup"><span data-stu-id="92038-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="92038-120">Quando viene visualizzato il **modello di progetto installato correttamente** , QDK è pronto per l'uso con le proprie applicazioni e librerie.</span><span class="sxs-lookup"><span data-stu-id="92038-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="92038-121">Per creare un nuovo progetto:</span><span class="sxs-lookup"><span data-stu-id="92038-121">To create a new project:</span></span>

1. <span data-ttu-id="92038-122">Fare clic su **Visualizza**  ->  **riquadro comandi** e selezionare **Q #: Crea nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="92038-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="92038-123">Fare clic su **applicazione console autonoma**.</span><span class="sxs-lookup"><span data-stu-id="92038-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="92038-124">Passare al percorso per salvare il progetto e fare clic su **Crea progetto**.</span><span class="sxs-lookup"><span data-stu-id="92038-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="92038-125">Quando il progetto viene creato correttamente, fare clic su **Apri nuovo progetto** in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="92038-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="92038-126">Esaminare il progetto.</span><span class="sxs-lookup"><span data-stu-id="92038-126">Inspect the project.</span></span> <span data-ttu-id="92038-127">Verrà visualizzato un file di origine denominato `Program.qs` , ovvero un programma Q # che definisce una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="92038-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="92038-128">Per eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="92038-128">To run the application:</span></span>
1. <span data-ttu-id="92038-129">Fare clic su **terminale**  ->  **nuovo terminale**.</span><span class="sxs-lookup"><span data-stu-id="92038-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="92038-130">Al prompt dei comandi, immettere `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="92038-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="92038-131">Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="92038-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="92038-132">Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione VS Code Q #.</span><span class="sxs-lookup"><span data-stu-id="92038-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="92038-133">Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.</span><span class="sxs-lookup"><span data-stu-id="92038-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="92038-134">Sviluppare con Q # con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92038-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="92038-135">Verificare l'installazione di Visual Studio creando un'applicazione Q # `Hello World` .</span><span class="sxs-lookup"><span data-stu-id="92038-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="92038-136">Per creare una nuova applicazione Q #:</span><span class="sxs-lookup"><span data-stu-id="92038-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="92038-137">Aprire Visual Studio e fare clic su **file**  ->  **nuovo**  ->  **progetto**.</span><span class="sxs-lookup"><span data-stu-id="92038-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="92038-138">Digitare `Q#` nella casella di ricerca, selezionare **Q # applicazione** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="92038-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="92038-139">Immettere un nome e un percorso per l'applicazione e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="92038-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="92038-140">Esaminare il progetto.</span><span class="sxs-lookup"><span data-stu-id="92038-140">Inspect the project.</span></span> <span data-ttu-id="92038-141">Verrà visualizzato un file di origine denominato `Program.qs` , ovvero un programma Q # che definisce una semplice operazione per stampare un messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="92038-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="92038-142">Per eseguire l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="92038-142">To run the application:</span></span>
1. <span data-ttu-id="92038-143">Selezionare **debug**  ->  **Avvia senza eseguire debug**.</span><span class="sxs-lookup"><span data-stu-id="92038-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="92038-144">Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="92038-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="92038-145">Se si dispone di più progetti all'interno di una soluzione di Visual Studio, tutti i progetti contenuti nella soluzione devono trovarsi nella stessa cartella della soluzione o in una delle relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="92038-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="92038-146">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="92038-146">Next steps</span></span>

<span data-ttu-id="92038-147">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="92038-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
