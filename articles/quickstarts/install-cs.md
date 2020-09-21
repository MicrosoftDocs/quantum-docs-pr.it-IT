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
# <a name="develop-with-no-locq-and-net"></a>Sviluppare con Q# e .NET

Q# è progettato per essere eseguito correttamente con i linguaggi .NET, come C# e F#.
Questa guida illustra come usare Q# con un programma host scritto in un linguaggio .NET.

Prima di tutto si creano l'applicazione Q# e l'host .NET, quindi viene illustrato come eseguire una chiamata a Q# dall'host.

## <a name="prerequisites"></a>Prerequisiti

- Installare Quantum Development Kit [per l'uso con i progetti Q#](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-no-locq-library-and-a-net-host"></a>Creazione di una libreria Q# e di un host .NET

Il primo passaggio consiste nel creare progetti per la libreria Q# e per l'host .NET che verrà chiamato in operazioni e funzioni definite nella libreria Q#.

Seguire le istruzioni riportate nella scheda corrispondente al proprio ambiente di sviluppo.
Se si usa un editor diverso da Visual Studio o VS Code, seguire la procedura per il prompt dei comandi.

### <a name="visual-studio-code-or-command-prompt"></a>[Visual Studio Code o prompt dei comandi](#tab/tabid-cmdline)

- Creare una nuova libreria Q#

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Creare un nuovo progetto console C# o F#

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Aggiungere la libreria Q# come riferimento dal programma host

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [Facoltativo] Creare una soluzione per entrambi i progetti

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Creare una nuova libreria Q#
  - Passare a **File** -> **Nuovo** -> **Progetto**
  - Digitare "Q#" nella casella di ricerca
  - Selezionare la **libreria Q#**
  - Selezionare **Avanti**
  - Scegliere un nome e una posizione per la libreria
  - Assicurarsi che l'opzione "Inserisci soluzione e progetto nella stessa directory" sia **deselezionata**
  - Selezionare **Crea**
- Creare un nuovo programma host C# o F#
  - Passare a **File** → **Nuovo** → **Progetto**
  - Selezionare "App console (.NET Core)" per C# o F#
  - Selezionare **Avanti**
  - In *Soluzione* selezionare "Aggiungi a soluzione"
  - Scegliere un nome per il programma host
  - Selezionare **Crea**

***

## <a name="calling-into-no-locq-from-net"></a>Chiamata in Q# da .NET

Dopo aver configurato i progetti seguendo le istruzioni riportate in precedenza, è possibile eseguire chiamate in Q# dall'applicazione console .NET.
Il compilatoreQ# creerà le classi .NET per ogni funzione e operazione Q# che consentono di eseguire i programmi quantistici in un simulatore.

Ad esempio, l'[esempio di interoperabilità .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) include l'esempio seguente di un'operazione Q#:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Per chiamare questa operazione da .NET in un simulatore quantistico, è possibile usare il metodo `Run` della classe `RunAlgorithm` di .NET generata dal compilatore Q#:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Passaggi successivi

Ora che è stato configurato Quantum Development Kit per applicazioni Q# e per l'interoperabilità con .NET, è possibile scrivere ed eseguire il [primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).
