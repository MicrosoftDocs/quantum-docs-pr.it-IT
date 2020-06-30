---
title: Sviluppare con le applicazioni della riga di comando di Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274123"
---
# <a name="develop-with-q-command-line-applications"></a>Sviluppare con le applicazioni della riga di comando di Q#

I programmi Q# possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F# o Python.

## <a name="prerequisites"></a>Prerequisiti

- [.NET Core SDK 3.1 o versione successiva](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installazione

Anche se è possibile compilare applicazioni della riga di comando di Q# in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) o l'IDE di Visual Studio per le applicazioni di Q#. Lo sviluppo in questi strumenti consente di accedere a funzionalità avanzate.

Per configurare VS Code:

1. Scaricare e installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).
2. Installare [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Per configurare Visual Studio:

1. Scaricare e installare [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 o versione successiva, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato.
2. Scaricare e installare [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Sviluppare con Q# usando VS Code

Installare i modelli di progetto Q#:

1. Aprire VS Code.
2. Fare clic su **Visualizza** -> **Riquadro comandi**.
3. Selezionare **Q#: Install project templates** (Q#: Installa modelli di progetto).

Quando viene visualizzato il messaggio **Project templates installed successfully** (Modelli di progetto installati), il QDK è pronto per l'uso con applicazioni e librerie personalizzate.

Per creare un nuovo progetto:

1. Fare clic su **Visualizza** -> **Riquadro comandi** e selezionare **Q#: Create New Project** (Q#: Crea nuovo progetto).
2. Click **Standalone console application** (Applicazione console autonoma).
3. Passare al percorso in cui salvare il progetto e fare clic su **Create Project** (Crea progetto).
4. Al termine dell'operazione, fare clic su **Open new project** (Apri nuovo progetto) in basso a destra.
        
Esaminare il progetto. Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.

Per eseguire l'applicazione:
1. Fare clic su **Terminale** -> **Nuovo terminale**.
2. Al prompt del terminale, immettere `dotnet run`.
3. Nella finestra di output dovrebbe essere visualizzato il testo seguente: `Hello quantum world!`


> [!NOTE]
> Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Q# di VS Code. Se sono presenti più progetti all'interno di un'area di lavoro di VS Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.

## <a name="develop-with-q-using-visual-studio"></a>Sviluppare con C# usando Visual Studio

Verificare l'installazione di Visual Studio creando un'applicazione Q# `Hello World`.

Per creare una nuova applicazione Q#:
1. Aprire Visual Studio e fare clic su **File** -> **Nuovo** -> **Progetto**.
2. Digitare `Q#` nella casella di ricerca, selezionare **Q# Application** (Applicazione Q#) e quindi fare clic su **Avanti**.
3. Immettere un nome e un percorso per l'applicazione e fare clic su **Crea**.


Esaminare il progetto. Dovrebbe essere visualizzato un file di origine denominato `Program.qs`, che corrisponde a un programma Q# in cui viene definita una semplice operazione per stampare un messaggio nella console.

Per eseguire l'applicazione:
1. Selezionare **Debug** -> **Avvia senza eseguire debug**.
2. Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.

> [!NOTE]
> Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.  


## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).
