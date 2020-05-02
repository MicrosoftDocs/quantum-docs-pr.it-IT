---
title: Sviluppare con Q# + C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680172"
---
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="777a4-102">Uso di Q # con\# C e F\#</span><span class="sxs-lookup"><span data-stu-id="777a4-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="777a4-103">Q # è progettato per essere eseguito correttamente con i linguaggi .NET, ad esempio C# e F #.</span><span class="sxs-lookup"><span data-stu-id="777a4-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="777a4-104">In questa guida verrà illustrato come usare Q # con un programma host scritto in un linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="777a4-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="777a4-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="777a4-105">Prerequisites</span></span>

- <span data-ttu-id="777a4-106">Installare Quantum Development Kit [per l'uso con i progetti da riga di comando Q #](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="777a4-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="777a4-107">Creazione di una libreria Q # e di un host .NET</span><span class="sxs-lookup"><span data-stu-id="777a4-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="777a4-108">Il primo passaggio consiste nel creare progetti per la libreria Q # e per l'host .NET che chiamerà le operazioni e le funzioni definite nella libreria Q #.</span><span class="sxs-lookup"><span data-stu-id="777a4-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="777a4-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="777a4-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="777a4-110">Crea una nuova libreria Q #</span><span class="sxs-lookup"><span data-stu-id="777a4-110">Create a new Q# library</span></span>
  - <span data-ttu-id="777a4-111">Vai a **file** -> **nuovo** -> **progetto**</span><span class="sxs-lookup"><span data-stu-id="777a4-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="777a4-112">Digitare "Q #" nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="777a4-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="777a4-113">Seleziona **libreria Q #**</span><span class="sxs-lookup"><span data-stu-id="777a4-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="777a4-114">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="777a4-114">Select **Next**</span></span>
  - <span data-ttu-id="777a4-115">Scegliere un nome e un percorso per la libreria</span><span class="sxs-lookup"><span data-stu-id="777a4-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="777a4-116">Verificare che "posiziona progetto e soluzione nella stessa directory" sia **deselezionata**</span><span class="sxs-lookup"><span data-stu-id="777a4-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="777a4-117">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="777a4-117">Select **Create**</span></span>
- <span data-ttu-id="777a4-118">Creare un nuovo programma host C# o F #</span><span class="sxs-lookup"><span data-stu-id="777a4-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="777a4-119">Vai a **file** → **nuovo** → **progetto**</span><span class="sxs-lookup"><span data-stu-id="777a4-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="777a4-120">Selezionare "app console (.NET Core") "per C# o F #</span><span class="sxs-lookup"><span data-stu-id="777a4-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="777a4-121">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="777a4-121">Select **Next**</span></span>
  - <span data-ttu-id="777a4-122">In *soluzione*selezionare "Aggiungi a soluzione".</span><span class="sxs-lookup"><span data-stu-id="777a4-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="777a4-123">Scegliere un nome per il programma host</span><span class="sxs-lookup"><span data-stu-id="777a4-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="777a4-124">Selezionare **Crea**</span><span class="sxs-lookup"><span data-stu-id="777a4-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="777a4-125">Visual Studio Code o riga di comando</span><span class="sxs-lookup"><span data-stu-id="777a4-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="777a4-126">Crea una nuova libreria Q #</span><span class="sxs-lookup"><span data-stu-id="777a4-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="777a4-127">Creare un nuovo progetto console C# o F #</span><span class="sxs-lookup"><span data-stu-id="777a4-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="777a4-128">Aggiungere la libreria Q # come riferimento dal programma host</span><span class="sxs-lookup"><span data-stu-id="777a4-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="777a4-129">Opzionale Creare una soluzione per entrambi i progetti</span><span class="sxs-lookup"><span data-stu-id="777a4-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="777a4-130">Chiamata a Q # da .NET</span><span class="sxs-lookup"><span data-stu-id="777a4-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="777a4-131">Dopo aver configurato i progetti seguendo le istruzioni riportate sopra, è possibile chiamare Q # dall'applicazione console .NET.</span><span class="sxs-lookup"><span data-stu-id="777a4-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="777a4-132">Il compilatore Q # creerà le classi .NET per ogni operazione e funzione Q # che consentono di eseguire i programmi Quantum in un simulatore.</span><span class="sxs-lookup"><span data-stu-id="777a4-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="777a4-133">Ad esempio, l'esempio di [interoperabilità .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) include l'esempio seguente di un'operazione Q #:</span><span class="sxs-lookup"><span data-stu-id="777a4-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="777a4-134">Per chiamare questa operazione da .NET in un simulatore Quantum, è possibile usare `Run` il metodo della `RunAlgorithm` classe .NET generata dal compilatore Q #:</span><span class="sxs-lookup"><span data-stu-id="777a4-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="777a4-135">C#</span><span class="sxs-lookup"><span data-stu-id="777a4-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="777a4-136">F #</span><span class="sxs-lookup"><span data-stu-id="777a4-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="777a4-137">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="777a4-137">What's next?</span></span>

<span data-ttu-id="777a4-138">Ora che il kit di sviluppo Quantum è stato configurato per i programmi da riga di comando Q # e per l'interoperabilità con .NET, è possibile scrivere ed eseguire [il primo programma Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="777a4-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
