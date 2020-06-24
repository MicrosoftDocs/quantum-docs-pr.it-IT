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
# <a name="numerics-library-installation-and-validation"></a>Installazione e convalida della libreria Numerics

Quantum Development Kit fornisce il supporto per la funzionalità Numerics tramite il [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) pacchetto NuGet.

**Visual Studio >= 2019:** Se si usa Visual Studio 2019 o versione successiva, è possibile aggiungere il pacchetto numerico usando Gestione pacchetti NuGet.
A tale scopo, selezionare "Gestisci pacchetti NuGet". dalla voce di menu "Project" in Visual Studio.

Dalla scheda Sfoglia cercare il nome del pacchetto "Microsoft. Quantum. Numerics"

> [!NOTE]
> Assicurarsi di eseguire il segno di "Includi versione preliminare"

In questo elenco vengono elencati i pacchetti disponibili per il download.
Se si passa il puntatore del mouse su "Microsoft. Quantum. Numerics", viene visualizzata una freccia rivolta verso il basso a destra del numero di versione.
Per installare il pacchetto Numerics, fare clic sulla freccia.

Per ulteriori informazioni, vedere la [Guida dell'interfaccia utente di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-ui).

In alternativa, è possibile usare la console di gestione pacchetti per aggiungere la libreria Numerics al progetto tramite l'interfaccia della riga di comando.

![Usare la console di gestione pacchetti dalla riga di comando](~/media/vs2017-nuget-console-menu.png)

Dalla console di gestione pacchetti eseguire le operazioni seguenti:

```
Install-Package Microsoft.Quantum.Numerics
```

Per ulteriori informazioni, vedere la [Guida della console di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Riga di comando o Visual Studio Code:** Usando la riga di comando autonomamente o dall'interno di Visual Studio Code, è possibile usare il `dotnet` comando per aggiungere il riferimento al pacchetto NuGet al progetto:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Verifica dell'installazione

Come il resto del kit di sviluppo Quantum, la libreria Numerics viene fornita con esempi che consentono di iniziare il più rapidamente possibile.
Per testare l'installazione usando questi esempi, clonare il [repository principale degli esempi](https://github.com/Microsoft/Quantum) e quindi eseguire uno degli esempi.

Per eseguire l' [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) esempio:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
