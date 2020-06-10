---
title: 'Sviluppare con Q # e Python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630276"
---
# <a name="develop-with-q-and-python"></a>Sviluppare con Q # e Python

Installare QDK per sviluppare programmi host Python per chiamare le operazioni Q #.

1. Prerequisiti

    - [Python](https://www.python.org/downloads/) 3,6 o versione successiva
    - Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Installare il `qsharp` pacchetto, un pacchetto Python che consente l'interoperabilità tra Q # e Python.

    ```
    pip install qsharp
    ```

1. Installare IQ #, un kernel usato da Jupyter e Python che fornisce le funzionalità di base per la compilazione e l'esecuzione di operazioni Q #.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Se viene visualizzato un errore durante il `dotnet iqsharp install` passaggio, aprire una nuova finestra del terminale e riprovare.
    > Se questa operazione non funziona ancora, provare a individuare lo `dotnet-iqsharp` strumento installato (in Windows `dotnet-iqsharp.exe` ) e a eseguire:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello `dotnet-iqsharp` strumento nel file System.
    > Questa operazione si trova in genere `.dotnet/tools` nella cartella del profilo utente.
  
1. Sebbene sia possibile usare Q # con Python in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) IDE per le applicazioni Python Q # +. Utilizzando Visual Studio Code e l'estensione di Visual Studio Code QDK è possibile accedere a funzionalità più avanzate.

    - Installare [vs code](https://code.visualstudio.com/download) (Windows, Linux e Mac)
    - Installare l' [estensione QDK per vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

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
> * È anche possibile usare i notebook di Jupyter Python per scrivere il programma Python classico e chiamare le operazioni Q # dalle celle. Il codice Python è semplicemente un normale programma Python.

## <a name="next-steps"></a>Passaggi successivi

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).
