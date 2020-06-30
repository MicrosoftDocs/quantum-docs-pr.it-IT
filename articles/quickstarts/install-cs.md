---
title: Sviluppare con Q# e .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274089"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="26f9f-102">Sviluppare con Q# e .NET</span><span class="sxs-lookup"><span data-stu-id="26f9f-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="26f9f-103">Q# è progettato per essere eseguito correttamente con i linguaggi .NET, come C# e F#.</span><span class="sxs-lookup"><span data-stu-id="26f9f-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="26f9f-104">Questa guida illustra come usare Q# con un programma host scritto in un linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="26f9f-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26f9f-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="26f9f-105">Prerequisites</span></span>

- <span data-ttu-id="26f9f-106">Installare Quantum Development Kit [per l'uso con i progetti della riga di comando di Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="26f9f-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="26f9f-107">Creazione di una libreria Q# e di un host .NET</span><span class="sxs-lookup"><span data-stu-id="26f9f-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="26f9f-108">Il primo passaggio consiste nel creare progetti per la libreria Q# e per l'host .NET che verrà chiamato in operazioni e funzioni definite nella libreria Q#.</span><span class="sxs-lookup"><span data-stu-id="26f9f-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="26f9f-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="26f9f-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="26f9f-110">Creare una nuova libreria Q#</span><span class="sxs-lookup"><span data-stu-id="26f9f-110">Create a new Q# library</span></span>
  - <span data-ttu-id="26f9f-111">Passare a **File** -> **Nuovo** -> **Progetto**</span><span class="sxs-lookup"><span data-stu-id="26f9f-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="26f9f-112">Digitare "Q#" nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="26f9f-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="26f9f-113">Selezionare **Q# Library** (Libreria Q#)</span><span class="sxs-lookup"><span data-stu-id="26f9f-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="26f9f-114">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="26f9f-114">Select **Next**</span></span>
  - <span data-ttu-id="26f9f-115">Scegliere un nome e una posizione per la libreria</span><span class="sxs-lookup"><span data-stu-id="26f9f-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="26f9f-116">Assicurarsi che l'opzione "Inserisci soluzione e progetto nella stessa directory" sia **deselezionata**</span><span class="sxs-lookup"><span data-stu-id="26f9f-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="26f9f-117">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="26f9f-117">Select **Create**</span></span>
- <span data-ttu-id="26f9f-118">Creare un nuovo programma host C# o F#</span><span class="sxs-lookup"><span data-stu-id="26f9f-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="26f9f-119">Passare a **File** → **Nuovo** → **Progetto**</span><span class="sxs-lookup"><span data-stu-id="26f9f-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="26f9f-120">Selezionare "App console (.NET Core)" per C# o F#</span><span class="sxs-lookup"><span data-stu-id="26f9f-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="26f9f-121">Selezionare **Avanti**</span><span class="sxs-lookup"><span data-stu-id="26f9f-121">Select **Next**</span></span>
  - <span data-ttu-id="26f9f-122">In *Soluzione* selezionare "Aggiungi a soluzione"</span><span class="sxs-lookup"><span data-stu-id="26f9f-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="26f9f-123">Scegliere un nome per il programma host</span><span class="sxs-lookup"><span data-stu-id="26f9f-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="26f9f-124">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="26f9f-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="26f9f-125">Visual Studio Code o riga di comando</span><span class="sxs-lookup"><span data-stu-id="26f9f-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="26f9f-126">Creare una nuova libreria Q#</span><span class="sxs-lookup"><span data-stu-id="26f9f-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="26f9f-127">Creare un nuovo progetto console C# o F#</span><span class="sxs-lookup"><span data-stu-id="26f9f-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="26f9f-128">Aggiungere la libreria Q# come riferimento dal programma host</span><span class="sxs-lookup"><span data-stu-id="26f9f-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="26f9f-129">[Facoltativo] Creare una soluzione per entrambi i progetti</span><span class="sxs-lookup"><span data-stu-id="26f9f-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="26f9f-130">Chiamata in Q# da .NET</span><span class="sxs-lookup"><span data-stu-id="26f9f-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="26f9f-131">Dopo aver configurato i progetti seguendo le istruzioni riportate in precedenza, è possibile eseguire chiamate in Q# dall'applicazione console .NET.</span><span class="sxs-lookup"><span data-stu-id="26f9f-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="26f9f-132">Il compilatore Q# creerà le classi .NET per ogni operazione e funzione di Q# che consentono di eseguire i programmi quantistici in un simulatore.</span><span class="sxs-lookup"><span data-stu-id="26f9f-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="26f9f-133">Ad esempio, l'[esempio di interoperabilità .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) include l'esempio seguente di un'operazione di Q#:</span><span class="sxs-lookup"><span data-stu-id="26f9f-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="26f9f-134">Per chiamare questa operazione da .NET in un simulatore quantistico, è possibile usare il metodo `Run` della classe `RunAlgorithm` di .NET generata dal compilatore Q#:</span><span class="sxs-lookup"><span data-stu-id="26f9f-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="26f9f-135">C#</span><span class="sxs-lookup"><span data-stu-id="26f9f-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="26f9f-136">F#</span><span class="sxs-lookup"><span data-stu-id="26f9f-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="26f9f-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="26f9f-137">Next steps</span></span>

<span data-ttu-id="26f9f-138">Ora che è stato configurato Quantum Development Kit per i programmi da riga di comando di Q# e per l'interoperabilità con .NET, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="26f9f-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
