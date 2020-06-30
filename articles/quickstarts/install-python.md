---
title: Sviluppare con Q# e Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274083"
---
# <a name="develop-with-q-and-python"></a>Sviluppare con Q# e Python

Installare il QDK per sviluppare programmi host Python che chiamino operazioni Q#.

1. Prerequisiti

    - [Python](https://www.python.org/downloads/) 3.6 o versione successiva
    - Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Installare `qsharp`, un pacchetto Python che consente l'interoperabilità tra Q# e Python.

    ```
    pip install qsharp
    ```

1. Installare IQ#, un kernel usato principalmente da Jupyter e Python che fornisce le funzionalità essenziali per la compilazione e l'esecuzione di operazioni Q#.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Se durante il passaggio `dotnet iqsharp install` viene visualizzato un errore, aprire una nuova finestra del terminale e riprovare.
    > Se il problema persiste, provare a individuare lo strumento `dotnet-iqsharp` installato (in Windows `dotnet-iqsharp.exe`) ed eseguire:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello strumento `dotnet-iqsharp` nel file system.
    > Tale strumento si trova in genere in `.dotnet/tools` nella cartella del profilo utente.
  
1. Anche se è possibile usare Q# con Python in qualsiasi IDE, è consigliabile usare l'IDE di Visual Studio Code (VS Code) per le applicazioni che combinano Q# e Python. Usando Visual Studio Code e l'estensione Visual Studio Code QDK è possibile accedere a funzionalità più avanzate.

    - Installare [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).
    - Installare l'[estensione QDK per VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Verificare l'installazione creando un'applicazione `Hello World`

    - Creare un'operazione Q# minima creando un file denominato `Operation.qs` e aggiungendovi il codice seguente:

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - Creare un programma Python denominato `hello_world.py` per chiamare l'operazione `SayHello()` Q#:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Eseguire il programma:

        ```
        python hello_world.py
        ```

    - Verificare l'output. Il programma restituirà le righe seguenti:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * È anche possibile usare i notebook di Jupyter Python per scrivere il programma Python classico e chiamare le operazioni Q# dalle celle. Il codice Python è un normale programma Python.

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).
