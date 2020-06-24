---
title: Classificazione di base con la libreria Quantum Machine Learning
description: 'Informazioni su come eseguire un classificatore sequenziale quantistico scritto in Q # usando la libreria Quantum Machine Learning di Microsoft QDK.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275038"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Classificazione di base: classificare i dati con QDK

In questa Guida introduttiva si apprenderà come eseguire un classificatore sequenziale quantistico scritto in Q # usando la libreria Quantum Machine Learning della QDK. 

In questa guida verrà usato il set di dati Half-Moon, usando una struttura di classificazione definita in Q #.

## <a name="prerequisites"></a>Prerequisiti

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Creare un progetto Q # per un programma [host Python](xref:microsoft.quantum.install.python) o un [programma host C#](xref:microsoft.quantum.install.cs).

## <a name="host-program"></a>Programma host

Il programma host è costituito da tre parti:

- Caricare il set di dati e scegliere un set di parametri iniziali per il modello.
- Eseguire il training per determinare i parametri e la distorsione del modello.
- Convalidare il modello per determinarne l'accuratezza

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python con Visual Studio Code o riga di comando](#tab/tabid-python)

    Per eseguire il classificatore Q # da Python, salvare il codice seguente come `host.py` . Tenere presente che è necessario anche il file Q # `Training.qs` illustrato più avanti in questa esercitazione.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    È quindi possibile eseguire il programma host Python dalla riga di comando:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# con Visual Studio Code o riga di comando](#tab/tabid-csharp)

    Per eseguire il classificatore Q # da C#, salvare il codice seguente come `Host.cs` . Tenere presente che è necessario anche il file Q # `Training.qs` illustrato più avanti in questa esercitazione.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    È quindi possibile eseguire il programma host C# dalla riga di comando:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# con Visual Studio 2019](#tab/tabid-vs2019)

    Per eseguire il nuovo programma Q # da C# in Visual Studio, modificare `Host.cs` in modo da includere il codice C# seguente. Tenere presente che è necessario anche il file Q # `Training.qs` illustrato più avanti in questa esercitazione.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Premere quindi F5. L'esecuzione del programma verrà avviata e verrà visualizzata una nuova finestra con i risultati seguenti: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>\#Codice di classificazione Q

A questo punto è possibile vedere in che modo le operazioni richiamate dal programma host sono definite in Q #.
Il codice seguente viene salvato in un file denominato `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Le funzioni e le operazioni più importanti definite nel codice precedente sono:

- `ClassifierStructure() : ControlledRotation[]`: in questa funzione è stata impostata la struttura del modello di circuito aggiungendo i livelli delle attività di controllo controllate. Questo passaggio è analogo alla dichiarazione di livelli di neuroni in un modello di apprendimento avanzato sequenziale.
- `TrainHalfMoonModel() : (Double[], Double)`: questa operazione è la parte principale del codice e definisce il training. Qui si caricano gli esempi dal set di dati incluso nella libreria, si impostano i parametri Hyper e i parametri iniziali per il training e si avvia il training chiamando l'operazione `TrainSequentialClassifier` inclusa nella libreria. Restituisce i parametri e la distorsione che determinano il classificatore.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: questa operazione definisce il processo di convalida per la valutazione del modello. Qui vengono caricati gli esempi per la convalida, il numero di misure per campione e la tolleranza. Restituisce il numero di classificazioni non configurate nel batch di campioni scelto per la convalida.

## <a name="next-steps"></a>Passaggi successivi

In primo luogo, è possibile riprodurre il codice e provare a modificare alcuni parametri per vedere come influiscono sul training. Quindi, nell'esercitazione successiva, [progettare un classificatore personalizzato](xref:microsoft.quantum.libraries.machine-learning.design), si apprenderà come definire la struttura del classificatore.
