---
title: 'Eseguire programmi Q # senza un driver e una lingua host'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706802"
---
# <a name="q-command-line-applications"></a>Domande della riga di comando Q #

I programmi Q # possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F # o Python.

## <a name="pre-requisites"></a>Prerequisiti

- [.NET Core SDK 3,1 o versione successiva](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installazione

Sebbene sia possibile compilare applicazioni della riga di comando di Q # in qualsiasi IDE, si consiglia vivamente di usare Visual Studio Code (VS Code) o l'IDE di Visual Studio per le applicazioni Q #. Utilizzando VS Code o Visual Studio e l'estensione di Visual Studio Code QDK è possibile accedere a funzionalità più avanzate.

- Installare [vs code](https://code.visualstudio.com/download) (Windows, Linux e Mac)
- Installare l' [estensione QDK per vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) o
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, con il carico di lavoro per lo sviluppo multipiattaforma .NET Core abilitato
- Scaricare e installare l' [estensione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>Sviluppare con Q # usando VS Code

Installare i modelli di progetto di calcolo quantistico:

- Vai a **Visualizza** -> **riquadro comandi**
- Selezionare **Q #: installare i modelli di progetto**

Quantum Development Kit è ora installato e pronto per l'uso nelle applicazioni e nelle librerie.
- Creare un nuovo progetto:
  - Vai a **Visualizza** -> **riquadro comandi**
  - Selezionare **Q #: Crea nuovo progetto**
  - Seleziona **applicazione console autonoma**
  - Passare al percorso del file system in cui si vuole creare l'applicazione
  - Al termine della creazione del progetto, fare clic sul pulsante **Apri nuovo progetto...**
        
- Esaminare il progetto
  - Dovrebbe essere visualizzato un file denominato `Program.qs` created, ovvero un programma Q # che definisce una semplice operazione per stampare un messaggio nella console.

- Eseguire l'applicazione:
  - Vai a **Terminal** -> **New Terminal**
  - Immettere `dotnet run`
  - Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`


> [!NOTE]
> * Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione Visual Studio Code. Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.

## <a name="develop-with-q-using-visual-studio"></a>Sviluppare con Q # con Visual Studio

Verificare l'installazione creando un'applicazione `Hello World`

- Creare una nuova applicazione Q#
  - Vai a **file** -> **nuovo** -> **progetto**
  - Digitare `Q#` nella casella di ricerca
  - Selezionare **Applicazione Q#**
  - Fare clic su **Avanti**.
  - Scegliere un nome e una posizione per l'applicazione
  - Selezionare **Crea**

- Esaminare il progetto
  - Si noterà che è stato creato un `Program.qs` file denominato, ovvero un programma Q # che definisce una semplice operazione per stampare un messaggio nella console.

- Eseguire l'applicazione
  - Selezionare **debug** -> **Avvia senza eseguire debug**
  - Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.

> [!NOTE]
> * Se sono presenti più progetti all'interno di una soluzione di Visual Studio, è necessario che tutti i progetti contenuti nella soluzione si trovino nella stessa cartella della soluzione o in una delle relative sottocartelle.  


## <a name="whats-next"></a>Quali sono le operazioni successive?

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).
