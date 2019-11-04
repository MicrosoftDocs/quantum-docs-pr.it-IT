---
title: Informazioni su come aggiornare il Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185852"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aggiornare il Microsoft Quantum Development Kit (QDK)

Informazioni su come aggiornare la Microsoft Quantum Development Kit (QDK) alla versione più recente.

In questo articolo si presuppone che QDK sia già installato. Se si sta installando per la prima volta, consultare la Guida all' [installazione](xref:microsoft.quantum.install).

I passaggi di aggiornamento dipendono dall'ambiente di sviluppo. Scegliere l'ambiente nelle sezioni seguenti.

## <a name="python"></a>Python

1. Aggiornare il kernel `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificare la versione di `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Dovrebbe venire visualizzato l'output seguente.

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. Aggiornare il pacchetto di `qsharp`

    ```bash
    pip install qsharp --upgrade
    ```

1. Verificare la versione di `qsharp`

    ```bash
    pip show qsharp
    ```

    Dovrebbe venire visualizzato l'output seguente.

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. È ora possibile usare la versione aggiornata di QDK per eseguire i programmi Quantum esistenti.

## <a name="jupyter-notebooks"></a>Jupyter Notebook

1. Aggiornare il kernel `iqsharp`

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificare la versione di `iqsharp`

    ```bash
    dotnet iqsharp --version
    ```

    Dovrebbe venire visualizzato l'output seguente.

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. È ora possibile aprire un notebook di Jupyter esistente ed eseguirlo con il QDK aggiornato.

## <a name="c-on-windows-using-visual-studio"></a>C#in Windows con Visual Studio

1. Aggiornare l'estensione di Visual Studio Q #

    - Visual Studio richiede di accettare gli aggiornamenti all' [estensione Quantum di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Accetta l'aggiornamento

    > [!NOTE]
    > I modelli di progetto vengono aggiornati con l'estensione. I modelli aggiornati si applicano solo ai progetti appena creati. Il codice per i progetti esistenti non viene aggiornato quando viene aggiornata l'estensione.

1. Aggiornare i pacchetti QDK

    - Apri un'applicazione esistente
    - Selezionare le **dipendenze** nella Esplora soluzioni
    - Selezionare **Gestisci pacchetti NuGet**
    - Aggiornare i pacchetti **Microsoft. Quantum** alla versione più recente

1. È ora possibile eseguire l'applicazione con la versione più recente di QDK.

## <a name="c-using-vs-code"></a>C#, utilizzo di VS Code

1. Aggiornare l'estensione VS Code Quantum

    - Riavvia VS Code
    - Passare alla scheda **estensioni**
    - Selezionare l' **Microsoft Quantum Development Kit per Visual Studio Code** estensione
    - Ricarica l'estensione

1. Aggiornare i modelli di progetto Quantum:

   - Vai a **visualizza** -> **riquadro comandi**
   - Selezionare **Q #: installare i modelli di progetto**

1. Aprire un'applicazione esistente in VS Code

   - Modificare il file con estensione csproj per aggiungere le nuove versioni del pacchetto

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    Se si usano altri pacchetti `Microsoft.Quantum`, aggiornarli.

1. È ora possibile eseguire l'applicazione con la QDK aggiornata

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, uso dello strumento da riga di comando `dotnet`

1. Aggiornare i modelli di progetto Quantum per .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Aggiornare ed eseguire un'applicazione esistente

    - Aggiornare le versioni del pacchetto QDK nell'applicazione

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        Se l'applicazione usa altri pacchetti di `Microsoft.Quantum`, aggiornarli.

    - Eseguire l'applicazione

        ```bash
        dotnet run
        ```

    - L'applicazione viene eseguita con le nuove versioni del pacchetto

## <a name="whats-next"></a>Potrai anche

Ora che è stato aggiornato Quantum Development Kit nell'ambiente preferito, è possibile continuare a sviluppare ed eseguire i programmi Quantum. Se non è ancora stato scritto un programma, è possibile iniziare a usare [il primo programma Quantum](xref:microsoft.quantum.write-program).
