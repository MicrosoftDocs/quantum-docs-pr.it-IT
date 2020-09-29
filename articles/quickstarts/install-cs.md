---
title: Sviluppare con Q# e .NET
description: Informazioni su come creare un'applicazione Q# con linguaggi .NET.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8733918daa02afaea0fc1994d5f0851d4be9b93
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834330"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="6054b-103">Sviluppare con Q# e .NET</span><span class="sxs-lookup"><span data-stu-id="6054b-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="6054b-104">Q# è progettato per essere eseguito correttamente con i linguaggi .NET, come C# e F#.</span><span class="sxs-lookup"><span data-stu-id="6054b-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="6054b-105">Questa guida illustra come usare Q# con un programma host scritto in un linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="6054b-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="6054b-106">Prima di tutto si creano l'applicazione Q# e l'host .NET, quindi viene illustrato come eseguire una chiamata a Q# dall'host.</span><span class="sxs-lookup"><span data-stu-id="6054b-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6054b-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6054b-107">Prerequisites</span></span>

- <span data-ttu-id="6054b-108">Installare Quantum Development Kit [per l'uso con i progetti Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="6054b-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="6054b-109">Creazione di una libreria Q# e di un host .NET</span><span class="sxs-lookup"><span data-stu-id="6054b-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="6054b-110">Il primo passaggio consiste nel creare progetti per la libreria Q# e per l'host .NET che verrà chiamato in operazioni e funzioni definite nella libreria Q#.</span><span class="sxs-lookup"><span data-stu-id="6054b-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="6054b-111">Seguire le istruzioni riportate nella scheda corrispondente al proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="6054b-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="6054b-112">Se si usa un editor diverso da Visual Studio o VS Code, seguire la procedura per il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="6054b-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="6054b-113">Visual Studio Code o prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="6054b-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="6054b-114">Creare una nuova libreria Q#</span><span class="sxs-lookup"><span data-stu-id="6054b-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="6054b-115">Creare un nuovo progetto console C# o F#</span><span class="sxs-lookup"><span data-stu-id="6054b-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="6054b-116">Aggiungere la libreria Q# come riferimento dal programma host</span><span class="sxs-lookup"><span data-stu-id="6054b-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="6054b-117">[Facoltativo] Creare una soluzione per entrambi i progetti</span><span class="sxs-lookup"><span data-stu-id="6054b-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="6054b-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6054b-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="6054b-119">Creare una nuova libreria Q#</span><span class="sxs-lookup"><span data-stu-id="6054b-119">Create a new Q# library</span></span>
  - <span data-ttu-id="6054b-120">Passare a **File** -> **Nuovo** -> **Progetto**</span><span class="sxs-lookup"><span data-stu-id="6054b-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="6054b-121">Digitare "Q#" nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="6054b-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="6054b-122">Selezionare la **libreria Q#**</span><span class="sxs-lookup"><span data-stu-id="6054b-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="6054b-123">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="6054b-123">Select **Next**</span></span>
  - <span data-ttu-id="6054b-124">Scegliere un nome e una posizione per la libreria</span><span class="sxs-lookup"><span data-stu-id="6054b-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="6054b-125">Assicurarsi che l'opzione "Inserisci soluzione e progetto nella stessa directory" sia **deselezionata**</span><span class="sxs-lookup"><span data-stu-id="6054b-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="6054b-126">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="6054b-126">Select **Create**</span></span>
- <span data-ttu-id="6054b-127">Creare un nuovo programma host C# o F#</span><span class="sxs-lookup"><span data-stu-id="6054b-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="6054b-128">Passare a **File** → **Nuovo** → **Progetto**</span><span class="sxs-lookup"><span data-stu-id="6054b-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="6054b-129">Selezionare "App console (.NET Core)" per C# o F#</span><span class="sxs-lookup"><span data-stu-id="6054b-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="6054b-130">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="6054b-130">Select **Next**</span></span>
  - <span data-ttu-id="6054b-131">In *Soluzione* selezionare "Aggiungi a soluzione"</span><span class="sxs-lookup"><span data-stu-id="6054b-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="6054b-132">Scegliere un nome per il programma host</span><span class="sxs-lookup"><span data-stu-id="6054b-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="6054b-133">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="6054b-133">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="6054b-134">Chiamata in Q# da .NET</span><span class="sxs-lookup"><span data-stu-id="6054b-134">Calling into Q# from .NET</span></span>

<span data-ttu-id="6054b-135">Dopo aver configurato i progetti seguendo le istruzioni riportate in precedenza, è possibile eseguire chiamate in Q# dall'applicazione console .NET.</span><span class="sxs-lookup"><span data-stu-id="6054b-135">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="6054b-136">Il compilatoreQ# creerà le classi .NET per ogni funzione e operazione Q# che consentono di eseguire i programmi quantistici in un simulatore.</span><span class="sxs-lookup"><span data-stu-id="6054b-136">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="6054b-137">Ad esempio, l'[esempio di interoperabilità .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) include l'esempio seguente di un'operazione Q#:</span><span class="sxs-lookup"><span data-stu-id="6054b-137">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="6054b-138">Per chiamare questa operazione da .NET in un simulatore quantistico, è possibile usare il metodo `Run` della classe `RunAlgorithm` di .NET generata dal compilatore Q#:</span><span class="sxs-lookup"><span data-stu-id="6054b-138">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="6054b-139">C#</span><span class="sxs-lookup"><span data-stu-id="6054b-139">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="6054b-140">F#</span><span class="sxs-lookup"><span data-stu-id="6054b-140">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="6054b-141">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6054b-141">Next steps</span></span>

<span data-ttu-id="6054b-142">Ora che è stato configurato Quantum Development Kit per applicazioni Q# e per l'interoperabilità con .NET, è possibile scrivere ed eseguire il [primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="6054b-142">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
