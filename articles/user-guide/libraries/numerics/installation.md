---
title: Libreria Quantum Numerics Microsoft-installazione e convalida
description: Informazioni su come aggiungere la libreria Microsoft Quantum Numerics all'installazione di Visual Studio 2019 o versione successiva.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276132"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="6f332-103">Installazione e convalida della libreria Numerics</span><span class="sxs-lookup"><span data-stu-id="6f332-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="6f332-104">Quantum Development Kit fornisce il supporto per la funzionalità Numerics tramite il [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="6f332-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="6f332-105">**Visual Studio >= 2019:** Se si usa Visual Studio 2019 o versione successiva, è possibile aggiungere il pacchetto numerico usando Gestione pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="6f332-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="6f332-106">A tale scopo, selezionare "Gestisci pacchetti NuGet". dalla voce di menu "Project" in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6f332-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="6f332-107">Dalla scheda Sfoglia cercare il nome del pacchetto "Microsoft. Quantum. Numerics"</span><span class="sxs-lookup"><span data-stu-id="6f332-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="6f332-108">Assicurarsi di eseguire il segno di "Includi versione preliminare"</span><span class="sxs-lookup"><span data-stu-id="6f332-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="6f332-109">In questo elenco vengono elencati i pacchetti disponibili per il download.</span><span class="sxs-lookup"><span data-stu-id="6f332-109">This will list the packages available for download.</span></span>
<span data-ttu-id="6f332-110">Se si passa il puntatore del mouse su "Microsoft. Quantum. Numerics", viene visualizzata una freccia rivolta verso il basso a destra del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="6f332-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="6f332-111">Per installare il pacchetto Numerics, fare clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="6f332-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="6f332-112">Per ulteriori informazioni, vedere la [Guida dell'interfaccia utente di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="6f332-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="6f332-113">In alternativa, è possibile usare la console di gestione pacchetti per aggiungere la libreria Numerics al progetto tramite l'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6f332-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Usare la console di gestione pacchetti dalla riga di comando](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="6f332-115">Dalla console di gestione pacchetti eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f332-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="6f332-116">Per ulteriori informazioni, vedere la [Guida della console di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="6f332-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="6f332-117">**Riga di comando o Visual Studio Code:** Usando la riga di comando autonomamente o dall'interno di Visual Studio Code, è possibile usare il `dotnet` comando per aggiungere il riferimento al pacchetto NuGet al progetto:</span><span class="sxs-lookup"><span data-stu-id="6f332-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="6f332-118">Verifica dell'installazione</span><span class="sxs-lookup"><span data-stu-id="6f332-118">Verifying your installation</span></span>

<span data-ttu-id="6f332-119">Come il resto del kit di sviluppo Quantum, la libreria Numerics viene fornita con esempi che consentono di iniziare il più rapidamente possibile.</span><span class="sxs-lookup"><span data-stu-id="6f332-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="6f332-120">Per testare l'installazione usando questi esempi, clonare il [repository principale degli esempi](https://github.com/Microsoft/Quantum) e quindi eseguire uno degli esempi.</span><span class="sxs-lookup"><span data-stu-id="6f332-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="6f332-121">Per eseguire l' [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) esempio:</span><span class="sxs-lookup"><span data-stu-id="6f332-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
