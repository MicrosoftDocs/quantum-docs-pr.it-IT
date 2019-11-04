---
title: Installazione e convalida della libreria Numerics | Microsoft Docs
description: Installazione e convalida della libreria Numerics
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184628"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="85550-103">Installazione e convalida della libreria Numerics</span><span class="sxs-lookup"><span data-stu-id="85550-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="85550-104">Quantum Development Kit fornisce il supporto per le funzionalità numeriche tramite il pacchetto NuGet [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .</span><span class="sxs-lookup"><span data-stu-id="85550-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="85550-105">**Visual Studio > = 2019:** Se si usa Visual Studio 2019 o versione successiva, è possibile aggiungere il pacchetto numerico usando Gestione pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="85550-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="85550-106">A tale scopo, selezionare "Gestisci pacchetti NuGet". dalla voce di menu "Project" in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85550-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="85550-107">Dalla scheda Sfoglia cercare il nome del pacchetto "Microsoft. Quantum. Numerics"</span><span class="sxs-lookup"><span data-stu-id="85550-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="85550-108">Assicurarsi di eseguire il segno di "Includi versione preliminare"</span><span class="sxs-lookup"><span data-stu-id="85550-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="85550-109">In questo elenco vengono elencati i pacchetti disponibili per il download.</span><span class="sxs-lookup"><span data-stu-id="85550-109">This will list the packages available for download.</span></span>
<span data-ttu-id="85550-110">Se si passa il puntatore del mouse su "Microsoft. Quantum. Numerics", viene visualizzata una freccia rivolta verso il basso a destra del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="85550-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="85550-111">Per installare il pacchetto Numerics, fare clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="85550-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="85550-112">Per ulteriori informazioni, vedere la [Guida dell'interfaccia utente di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="85550-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="85550-113">In alternativa, è possibile usare la console di gestione pacchetti per aggiungere la libreria Numerics al progetto tramite l'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="85550-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="85550-114">Dalla console di gestione pacchetti eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85550-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="85550-115">Per ulteriori informazioni, vedere la [Guida della console di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="85550-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="85550-116">**Riga di comando o Visual Studio Code:** Usando la riga di comando autonomamente o dall'interno di Visual Studio Code, è possibile usare il comando `dotnet` per aggiungere il riferimento al pacchetto NuGet al progetto:</span><span class="sxs-lookup"><span data-stu-id="85550-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="85550-117">Verifica dell'installazione</span><span class="sxs-lookup"><span data-stu-id="85550-117">Verifying your installation</span></span>

<span data-ttu-id="85550-118">Come il resto del kit di sviluppo Quantum, la libreria Numerics viene fornita con esempi che consentono di iniziare il più rapidamente possibile.</span><span class="sxs-lookup"><span data-stu-id="85550-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="85550-119">Per testare l'installazione usando questi esempi, clonare il [repository principale degli esempi](https://github.com/Microsoft/Quantum) e quindi eseguire uno degli esempi.</span><span class="sxs-lookup"><span data-stu-id="85550-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="85550-120">Per eseguire l'esempio [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) :</span><span class="sxs-lookup"><span data-stu-id="85550-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```