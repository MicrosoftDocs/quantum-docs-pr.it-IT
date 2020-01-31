---
title: 'Sviluppare con Q # + Python'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831002"
---
# <a name="develop-with-q--python"></a>Sviluppare con Q # + Python

Installare QDK per sviluppare programmi host Python per chiamare le operazioni Q #.

1. Prerequisiti

    - [Python](https://www.python.org/downloads/) 3.6 o versione successiva
    - Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)
    - [.NET Core SDK 3,1 o versione successiva](https://www.microsoft.com/net/download)


1. Installare il pacchetto di `qsharp`, un pacchetto Python che consente l'interoperabilità tra Q # e Python.

    ```bash
    pip install qsharp
    ```

1. Installare `iqsharp`, un kernel usato da Jupyter e Python che fornisce la funzionalità di base per la compilazione e l'esecuzione di operazioni Q #.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
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

        ```bash
        python hello_world.py
        ```

    - Verificare l'output. Il programma restituirà le righe seguenti:

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * È anche possibile usare i notebook di Jupyter Python per scrivere il programma Python classico e chiamare le operazioni Q # dalle celle. Il codice Python è semplicemente un normale programma Python.

## <a name="whats-next"></a>Potrai anche

Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).
