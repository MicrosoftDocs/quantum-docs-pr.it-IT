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
# <a name="develop-with-q-and-python"></a><span data-ttu-id="1f391-102">Sviluppare con Q # e Python</span><span class="sxs-lookup"><span data-stu-id="1f391-102">Develop with Q# and Python</span></span>

<span data-ttu-id="1f391-103">Installare QDK per sviluppare programmi host Python per chiamare le operazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="1f391-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="1f391-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1f391-104">Prerequisites</span></span>

    - <span data-ttu-id="1f391-105">[Python](https://www.python.org/downloads/) 3,6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1f391-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="1f391-106">Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="1f391-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="1f391-107">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="1f391-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="1f391-108">Installare il `qsharp` pacchetto, un pacchetto Python che consente l'interoperabilità tra Q # e Python.</span><span class="sxs-lookup"><span data-stu-id="1f391-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="1f391-109">Installare IQ #, un kernel usato da Jupyter e Python che fornisce le funzionalità di base per la compilazione e l'esecuzione di operazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="1f391-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="1f391-110">Se viene visualizzato un errore durante il `dotnet iqsharp install` passaggio, aprire una nuova finestra del terminale e riprovare.</span><span class="sxs-lookup"><span data-stu-id="1f391-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="1f391-111">Se questa operazione non funziona ancora, provare a individuare lo `dotnet-iqsharp` strumento installato (in Windows `dotnet-iqsharp.exe` ) e a eseguire:</span><span class="sxs-lookup"><span data-stu-id="1f391-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="1f391-112">dove `/path/to/dotnet-iqsharp` deve essere sostituito con il percorso assoluto dello `dotnet-iqsharp` strumento nel file System.</span><span class="sxs-lookup"><span data-stu-id="1f391-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="1f391-113">Questa operazione si trova in genere `.dotnet/tools` nella cartella del profilo utente.</span><span class="sxs-lookup"><span data-stu-id="1f391-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="1f391-114">Sebbene sia possibile usare Q # con Python in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) IDE per le applicazioni Python Q # +.</span><span class="sxs-lookup"><span data-stu-id="1f391-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="1f391-115">Utilizzando Visual Studio Code e l'estensione di Visual Studio Code QDK è possibile accedere a funzionalità più avanzate.</span><span class="sxs-lookup"><span data-stu-id="1f391-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="1f391-116">Installare [vs code](https://code.visualstudio.com/download) (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="1f391-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="1f391-117">Installare l' [estensione QDK per vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="1f391-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="1f391-118">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="1f391-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1f391-119">Creare un'operazione Q# minima creando un file denominato `Operation.qs` e aggiungendovi il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1f391-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="1f391-120">Creare un programma Python denominato `hello_world.py` per chiamare l'operazione `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="1f391-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="1f391-121">Eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="1f391-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="1f391-122">Verificare l'output.</span><span class="sxs-lookup"><span data-stu-id="1f391-122">Verify the output.</span></span> <span data-ttu-id="1f391-123">Il programma restituirà le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f391-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="1f391-124">È anche possibile usare i notebook di Jupyter Python per scrivere il programma Python classico e chiamare le operazioni Q # dalle celle.</span><span class="sxs-lookup"><span data-stu-id="1f391-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="1f391-125">Il codice Python è semplicemente un normale programma Python.</span><span class="sxs-lookup"><span data-stu-id="1f391-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1f391-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1f391-126">Next steps</span></span>

<span data-ttu-id="1f391-127">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="1f391-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
