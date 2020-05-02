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
# <a name="using-q-with-c-and-f"></a>Uso di Q # con\# C e F\#

Q # è progettato per essere eseguito correttamente con i linguaggi .NET, ad esempio C# e F #.
In questa guida verrà illustrato come usare Q # con un programma host scritto in un linguaggio .NET.

## <a name="prerequisites"></a>Prerequisiti

- Installare Quantum Development Kit [per l'uso con i progetti da riga di comando Q #](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Creazione di una libreria Q # e di un host .NET

Il primo passaggio consiste nel creare progetti per la libreria Q # e per l'host .NET che chiamerà le operazioni e le funzioni definite nella libreria Q #.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Crea una nuova libreria Q #
  - Vai a **file** -> **nuovo** -> **progetto**
  - Digitare "Q #" nella casella di ricerca
  - Seleziona **libreria Q #**
  - Fare clic su **Avanti**.
  - Scegliere un nome e un percorso per la libreria
  - Verificare che "posiziona progetto e soluzione nella stessa directory" sia **deselezionata**
  - Selezionare **Crea**
- Creare un nuovo programma host C# o F #
  - Vai a **file** → **nuovo** → **progetto**
  - Selezionare "app console (.NET Core") "per C# o F #
  - Fare clic su **Avanti**.
  - In *soluzione*selezionare "Aggiungi a soluzione".
  - Scegliere un nome per il programma host
  - Selezionare **Crea**

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code o riga di comando](#tab/tabid-cmdline)

- Crea una nuova libreria Q #

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Creare un nuovo progetto console C# o F #

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Aggiungere la libreria Q # come riferimento dal programma host

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Opzionale Creare una soluzione per entrambi i progetti

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>Chiamata a Q # da .NET

Dopo aver configurato i progetti seguendo le istruzioni riportate sopra, è possibile chiamare Q # dall'applicazione console .NET.
Il compilatore Q # creerà le classi .NET per ogni operazione e funzione Q # che consentono di eseguire i programmi Quantum in un simulatore.

Ad esempio, l'esempio di [interoperabilità .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) include l'esempio seguente di un'operazione Q #:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Per chiamare questa operazione da .NET in un simulatore Quantum, è possibile usare `Run` il metodo della `RunAlgorithm` classe .NET generata dal compilatore Q #:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F #](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a>Quali sono le operazioni successive?

Ora che il kit di sviluppo Quantum è stato configurato per i programmi da riga di comando Q # e per l'interoperabilità con .NET, è possibile scrivere ed eseguire [il primo programma Quantum](xref:microsoft.quantum.write-program).
