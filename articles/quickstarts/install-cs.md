---
title: Sviluppare con Q# e .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 96a1d0d75f3ff7de11407fd76479cbae86ce7571
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759273"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="b2852-102">Sviluppare con Q# e .NET</span><span class="sxs-lookup"><span data-stu-id="b2852-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="b2852-103">Q# è progettato per essere eseguito correttamente con i linguaggi .NET, come C# e F#.</span><span class="sxs-lookup"><span data-stu-id="b2852-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="b2852-104">Questa guida illustra come usare Q# con un programma host scritto in un linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="b2852-104">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="b2852-105">Prima di tutto si creano l'applicazione Q# e l'host .NET, quindi viene illustrato come eseguire una chiamata a Q# dall'host.</span><span class="sxs-lookup"><span data-stu-id="b2852-105">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2852-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b2852-106">Prerequisites</span></span>

- <span data-ttu-id="b2852-107">Installare Quantum Development Kit [per l'uso con i progetti Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="b2852-107">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="b2852-108">Creazione di una libreria Q# e di un host .NET</span><span class="sxs-lookup"><span data-stu-id="b2852-108">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="b2852-109">Il primo passaggio consiste nel creare progetti per la libreria Q# e per l'host .NET che verrà chiamato in operazioni e funzioni definite nella libreria Q#.</span><span class="sxs-lookup"><span data-stu-id="b2852-109">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="b2852-110">Seguire le istruzioni riportate nella scheda corrispondente al proprio ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b2852-110">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="b2852-111">Se si usa un editor diverso da Visual Studio o VS Code, seguire la procedura per il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b2852-111">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="b2852-112">Visual Studio Code o prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b2852-112">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="b2852-113">Creare una nuova libreria Q#</span><span class="sxs-lookup"><span data-stu-id="b2852-113">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="b2852-114">Creare un nuovo progetto console C# o F#</span><span class="sxs-lookup"><span data-stu-id="b2852-114">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="b2852-115">Aggiungere la libreria Q# come riferimento dal programma host</span><span class="sxs-lookup"><span data-stu-id="b2852-115">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="b2852-116">[Facoltativo] Creare una soluzione per entrambi i progetti</span><span class="sxs-lookup"><span data-stu-id="b2852-116">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="b2852-117">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b2852-117">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="b2852-118">Creare una nuova libreria Q#</span><span class="sxs-lookup"><span data-stu-id="b2852-118">Create a new Q# library</span></span>
  - <span data-ttu-id="b2852-119">Passare a **File** -> **Nuovo** -> **Progetto**</span><span class="sxs-lookup"><span data-stu-id="b2852-119">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="b2852-120">Digitare "Q#" nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="b2852-120">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="b2852-121">Selezionare la **libreria Q#**</span><span class="sxs-lookup"><span data-stu-id="b2852-121">Select **Q# Library**</span></span>
  - <span data-ttu-id="b2852-122">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="b2852-122">Select **Next**</span></span>
  - <span data-ttu-id="b2852-123">Scegliere un nome e una posizione per la libreria</span><span class="sxs-lookup"><span data-stu-id="b2852-123">Choose a name and location for your library</span></span>
  - <span data-ttu-id="b2852-124">Assicurarsi che l'opzione "Inserisci soluzione e progetto nella stessa directory" sia **deselezionata**</span><span class="sxs-lookup"><span data-stu-id="b2852-124">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="b2852-125">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="b2852-125">Select **Create**</span></span>
- <span data-ttu-id="b2852-126">Creare un nuovo programma host C# o F#</span><span class="sxs-lookup"><span data-stu-id="b2852-126">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="b2852-127">Passare a **File** → **Nuovo** → **Progetto**</span><span class="sxs-lookup"><span data-stu-id="b2852-127">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="b2852-128">Selezionare "App console (.NET Core)" per C# o F#</span><span class="sxs-lookup"><span data-stu-id="b2852-128">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="b2852-129">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="b2852-129">Select **Next**</span></span>
  - <span data-ttu-id="b2852-130">In *Soluzione* selezionare "Aggiungi a soluzione"</span><span class="sxs-lookup"><span data-stu-id="b2852-130">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="b2852-131">Scegliere un nome per il programma host</span><span class="sxs-lookup"><span data-stu-id="b2852-131">Choose a name for your host program</span></span>
  - <span data-ttu-id="b2852-132">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="b2852-132">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="b2852-133">Chiamata in Q# da .NET</span><span class="sxs-lookup"><span data-stu-id="b2852-133">Calling into Q# from .NET</span></span>

<span data-ttu-id="b2852-134">Dopo aver configurato i progetti seguendo le istruzioni riportate in precedenza, è possibile eseguire chiamate in Q# dall'applicazione console .NET.</span><span class="sxs-lookup"><span data-stu-id="b2852-134">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="b2852-135">Il compilatoreQ# creerà le classi .NET per ogni funzione e operazione Q# che consentono di eseguire i programmi quantistici in un simulatore.</span><span class="sxs-lookup"><span data-stu-id="b2852-135">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="b2852-136">Ad esempio, l'[esempio di interoperabilità .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) include l'esempio seguente di un'operazione Q#:</span><span class="sxs-lookup"><span data-stu-id="b2852-136">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="b2852-137">Per chiamare questa operazione da .NET in un simulatore quantistico, è possibile usare il metodo `Run` della classe `RunAlgorithm` di .NET generata dal compilatore Q#:</span><span class="sxs-lookup"><span data-stu-id="b2852-137">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="b2852-138">C#</span><span class="sxs-lookup"><span data-stu-id="b2852-138">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="b2852-139">F#</span><span class="sxs-lookup"><span data-stu-id="b2852-139">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="b2852-140">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b2852-140">Next steps</span></span>

<span data-ttu-id="b2852-141">Ora che è stato configurato Quantum Development Kit per applicazioni Q# e per l'interoperabilità con .NET, è possibile scrivere ed eseguire il [primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="b2852-141">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
