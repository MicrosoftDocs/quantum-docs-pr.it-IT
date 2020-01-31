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
# <a name="develop-with-q--python"></a><span data-ttu-id="d9a9e-102">Sviluppare con Q # + Python</span><span class="sxs-lookup"><span data-stu-id="d9a9e-102">Develop with Q# + Python</span></span>

<span data-ttu-id="d9a9e-103">Installare QDK per sviluppare programmi host Python per chiamare le operazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="d9a9e-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="d9a9e-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d9a9e-104">Pre-requisites</span></span>

    - <span data-ttu-id="d9a9e-105">[Python](https://www.python.org/downloads/) 3.6 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="d9a9e-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="d9a9e-106">Gestione pacchetti Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="d9a9e-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="d9a9e-107">.NET Core SDK 3,1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="d9a9e-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="d9a9e-108">Installare il pacchetto di `qsharp`, un pacchetto Python che consente l'interoperabilità tra Q # e Python.</span><span class="sxs-lookup"><span data-stu-id="d9a9e-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="d9a9e-109">Installare `iqsharp`, un kernel usato da Jupyter e Python che fornisce la funzionalità di base per la compilazione e l'esecuzione di operazioni Q #.</span><span class="sxs-lookup"><span data-stu-id="d9a9e-109">Install `iqsharp`, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="d9a9e-110">Sebbene sia possibile usare Q # con Python in qualsiasi IDE, è consigliabile usare Visual Studio Code (VS Code) IDE per le applicazioni Python Q # +.</span><span class="sxs-lookup"><span data-stu-id="d9a9e-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="d9a9e-111">Utilizzando Visual Studio Code e l'estensione di Visual Studio Code QDK è possibile accedere a funzionalità più avanzate.</span><span class="sxs-lookup"><span data-stu-id="d9a9e-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="d9a9e-112">Installare [vs code](https://code.visualstudio.com/download) (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="d9a9e-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="d9a9e-113">Installare l' [estensione QDK per vs code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="d9a9e-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="d9a9e-114">Verificare l'installazione creando un'applicazione `Hello World`</span><span class="sxs-lookup"><span data-stu-id="d9a9e-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="d9a9e-115">Creare un'operazione Q# minima creando un file denominato `Operation.qs` e aggiungendovi il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d9a9e-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="d9a9e-116">Creare un programma Python denominato `hello_world.py` per chiamare l'operazione `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="d9a9e-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="d9a9e-117">Eseguire il programma:</span><span class="sxs-lookup"><span data-stu-id="d9a9e-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="d9a9e-118">Verificare l'output.</span><span class="sxs-lookup"><span data-stu-id="d9a9e-118">Verify the output.</span></span> <span data-ttu-id="d9a9e-119">Il programma restituirà le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9a9e-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="d9a9e-120">È anche possibile usare i notebook di Jupyter Python per scrivere il programma Python classico e chiamare le operazioni Q # dalle celle.</span><span class="sxs-lookup"><span data-stu-id="d9a9e-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="d9a9e-121">Il codice Python è semplicemente un normale programma Python.</span><span class="sxs-lookup"><span data-stu-id="d9a9e-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="d9a9e-122">Potrai anche</span><span class="sxs-lookup"><span data-stu-id="d9a9e-122">What's next?</span></span>

<span data-ttu-id="d9a9e-123">Ora che è stato installato Quantum Development Kit nell'ambiente preferito, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="d9a9e-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
