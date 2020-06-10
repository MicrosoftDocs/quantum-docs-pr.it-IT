---
title: 'Sviluppare con le applicazioni da riga di comando Q #'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630266"
---
# <a name="develop-with-q-command-line-applications"></a>Sviluppare con le applicazioni da riga di comando Q #

I programmi Q # possono essere eseguiti autonomamente, senza un driver in un linguaggio host come C#, F # o Python.

## <a name="prerequisites"></a>Prerequisiti

- [.NET Core SDK 3,1 o versione successiva](https://www.microsoft.com/net/download)

## <a name="installation"></a>Installazione

Sebbene sia possibile compilare applicazioni della riga di comando di Q # in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) o IDE di Visual Studio per le applicazioni Q #. Lo sviluppo in questi strumenti consente di accedere a funzionalità avanzate.

Per configurare VS Code:

1. Scaricare e installare [vs code](https://code.visualstudio.com/download) (Windows, Linux e Mac).
2. Installare [Microsoft QDK per vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Per configurare Visual Studio:

1. Scaricare e installare [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3 o versione successiva con il carico di lavoro sviluppo multipiattaforma .NET Core abilitato.
2. Scaricare e installare [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Sviluppare con Q # usando VS Code

Installare i modelli di progetto Q #:

1. Aprire Visual Studio Code.
2. Fare clic su **Visualizza**  ->  **riquadro comandi**.
3. Selezionare **Q #: install Project Templates**.

Quando viene visualizzato il **modello di progetto installato correttamente** , QDK è pronto per l'uso con le proprie applicazioni e librerie.

Per creare un nuovo progetto:

1. Fare clic su **Visualizza**  ->  **riquadro comandi** e selezionare **Q #: Crea nuovo progetto**.
2. Fare clic su **applicazione console autonoma**.
3. Passare al percorso per salvare il progetto e fare clic su **Crea progetto**.
4. Quando il progetto viene creato correttamente, fare clic su **Apri nuovo progetto** in basso a destra.
        
Esaminare il progetto. Verrà visualizzato un file di origine denominato `Program.qs` , ovvero un programma Q # che definisce una semplice operazione per stampare un messaggio nella console.

Per eseguire l'applicazione:
1. Fare clic su **terminale**  ->  **nuovo terminale**.
2. Al prompt dei comandi, immettere `dotnet run` .
3. Nella finestra di output verrà visualizzato il testo seguente: `Hello quantum world!`


> [!NOTE]
> Le aree di lavoro con più cartelle radice non sono attualmente supportate dall'estensione VS Code Q #. Se sono presenti più progetti all'interno di un'area di lavoro di Visual Studio Code, è necessario che tutti i progetti siano contenuti all'interno della stessa cartella radice.

## <a name="develop-with-q-using-visual-studio"></a>Sviluppare con Q # con Visual Studio

Verificare l'installazione di Visual Studio creando un'applicazione Q # `Hello World` .

Per creare una nuova applicazione Q #:
1. Aprire Visual Studio e fare clic su **file**  ->  **nuovo**  ->  **progetto**.
2. Digitare `Q#` nella casella di ricerca, selezionare **Q # applicazione** e fare clic su **Avanti**.
3. Immettere un nome e un percorso per l'applicazione e fare clic su **Crea**.


Esaminare il progetto. Verrà visualizzato un file di origine denominato `Program.qs` , ovvero un programma Q # che definisce una semplice operazione per stampare un messaggio nella console.

Per eseguire l'applicazione:
1. Selezionare **debug**  ->  **Avvia senza eseguire debug**.
2. Verrà visualizzato il testo `Hello quantum world!` stampato in una finestra della console.

> [!NOTE]
> Se si dispone di più progetti all'interno di una soluzione di Visual Studio, tutti i progetti contenuti nella soluzione devono trovarsi nella stessa cartella della soluzione o in una delle relative sottocartelle.  


## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).
