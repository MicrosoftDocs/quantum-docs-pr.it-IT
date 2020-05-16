---
title: Aggiornare Quantum Development Kit (QDK)
description: 'Viene descritto come aggiornare i progetti Q # e i Microsoft Quantum Development Kit alla versione corrente.'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 53f72f1d49ae32a5a8572a1cf68a66a1d9b45e4a
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426900"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aggiornare il Microsoft Quantum Development Kit (QDK)

Informazioni su come aggiornare la Microsoft Quantum Development Kit (QDK) alla versione più recente.

In questo articolo si presuppone che QDK sia già installato. Se si sta installando per la prima volta, consultare la Guida all' [installazione](xref:microsoft.quantum.install).

Si consiglia di tenersi aggiornati con la versione più recente di QDK. Seguire questa guida di aggiornamento per eseguire l'aggiornamento alla versione più recente di QDK. Il processo è costituito da due parti:
1. aggiornamento dei file e dei progetti Q # esistenti per allineare il codice con qualsiasi sintassi aggiornata
2. aggiornamento del QDK stesso per l'ambiente di sviluppo scelto 

## <a name="updating-q-projects"></a>Aggiornamento di progetti Q # 

Indipendentemente dal fatto che si usi C# o Python per ospitare le operazioni Q #, seguire queste istruzioni per aggiornare i progetti Q #.

1. Per prima cosa, verificare di avere la versione più recente di [.NET Core SDK 3,1](https://dotnet.microsoft.com/download). Eseguire il comando seguente nel prompt dei comandi:

    ```dotnetcli
    dotnet --version
    ```

    Verificare che l'output sia `3.1.100` o superiore. In caso contrario, installare la [versione più recente](https://dotnet.microsoft.com/download) e verificare di nuovo. Seguire quindi le istruzioni riportate di seguito, a seconda della configurazione (Visual Studio, Visual Studio Code o direttamente dalla riga di comando).

### <a name="update-q-projects-in-visual-studio"></a>Aggiornare i progetti Q # in Visual Studio
 
1. Eseguire l'aggiornamento alla versione più recente di Visual Studio 2019, vedere [qui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) per istruzioni
2. Aprire la soluzione in Visual Studio
3. Dal menu selezionare **Compila**  ->  **soluzione pulita**
4. In ognuno dei file con estensione csproj aggiornare il Framework di destinazione a `netcoreapp3.1` (o `netstandard2.1` se si tratta di un progetto di libreria).
    Ovvero modificare le righe nel formato:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Per ulteriori informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
5. Salvare e chiudere tutti i file nella soluzione
6. Selezionare **strumenti**dalla  ->  **riga di comando**  ->  **prompt dei comandi per gli sviluppatori**
7. Per ogni progetto nella soluzione, eseguire il comando seguente:

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Se i progetti usano qualsiasi altro pacchetto Microsoft. Quantum (ad esempio, Microsoft. Quantum. Numerics), eseguire il comando anche per questi.
8. Chiudere il prompt dei comandi e selezionare **Compila**  ->  **Compila soluzione** ( *non* selezionare Ricompila soluzione)

È ora possibile ignorare [l'aggiornamento dell'estensione QDK di Visual Studio](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Aggiornare i progetti Q # in Visual Studio Code

1. In Visual Studio Code aprire la cartella contenente il progetto da aggiornare
2. Selezionare **terminale**  ->  **nuovo terminale**
3. Seguire le istruzioni per l'aggiornamento usando la riga di comando (direttamente di seguito)

### <a name="update-q-projects-using-the-command-line"></a>Aggiornare i progetti Q # usando la riga di comando

1. Passare alla cartella contenente il file di progetto
2. Eseguire il comando seguente:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. In ognuno dei file con estensione csproj aggiornare il Framework di destinazione a `netcoreapp3.1` (o `netstandard2.1` se si tratta di un progetto di libreria).
    Ovvero modificare le righe nel formato:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Per ulteriori informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).
4. Eseguire il comando seguente:

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    Se il progetto usa altri pacchetti Microsoft. Quantum (ad esempio, Microsoft. Quantum. Numerics), eseguire il comando anche per questi.
5. Salvare e chiudere tutti i file.
6. Ripetere 1-4 per ogni dipendenza del progetto, quindi tornare alla cartella che contiene il progetto principale ed eseguire:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Con i progetti Q # ora aggiornati, seguire le istruzioni riportate di seguito per aggiornare il QDK stesso.

## <a name="updating-the-qdk"></a>Aggiornamento di QDK

Il processo di aggiornamento del QDK varia a seconda del linguaggio di sviluppo e dell'ambiente in uso.
Selezionare l'ambiente di sviluppo indicato di seguito.

* [Python: aggiornare l'estensione IQ #](#update-iq-for-python)
* [Notebook di Jupyter: aggiornare l'estensione IQ #](#update-iq-for-jupyter-notebooks)
* [Visual Studio: aggiornare l'estensione QDK](#update-visual-studio-qdk-extension)
* [VS Code: aggiornare l'estensione QDK](#update-vs-code-qdk-extension)
* [Riga di comando e C#: aggiornare i modelli di progetto](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a>Aggiornare IQ # per Python

1. Aggiornare il `iqsharp` kernel 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verificare la `iqsharp` versione

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Dovrebbe venire visualizzato l'output seguente.

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Non preoccuparti se la tua `iqsharp` versione è più alta, deve corrispondere alla versione [più recente](xref:microsoft.quantum.relnotes).

3. Aggiornare il `qsharp` pacchetto

    ```bash
    pip install qsharp --upgrade
    ```

4. Verificare la `qsharp` versione

    ```bash
    pip show qsharp
    ```

    Dovrebbe venire visualizzato l'output seguente.

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. Eseguire il comando seguente dal percorso dei `.qs` file

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. È ora possibile usare la versione aggiornata di QDK per eseguire i programmi Quantum esistenti.

### <a name="update-iq-for-jupyter-notebooks"></a>Aggiornare IQ # per i notebook di Jupyter

1. Aggiornare il `iqsharp` kernel

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. Verificare la `iqsharp` versione

    ```dotnetcli
    dotnet iqsharp --version
    ```

    L'output dovrebbe essere simile al seguente:

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    Non preoccuparti se la tua `iqsharp` versione è più alta, deve corrispondere alla versione [più recente](xref:microsoft.quantum.relnotes).

3. Eseguire il comando seguente da una cella nel Jupyter Notebook:

    ```
    %workspace reload
    ```

4. È ora possibile aprire un notebook di Jupyter esistente ed eseguirlo con il QDK aggiornato.

### <a name="update-visual-studio-qdk-extension"></a>Aggiorna l'estensione QDK di Visual Studio

1. Aggiornare l'estensione di Visual Studio Q #

    - Visual Studio richiede di accettare gli aggiornamenti all' [estensione Quantum di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Accetta l'aggiornamento

    > [!NOTE]
    > I modelli di progetto vengono aggiornati con l'estensione. I modelli aggiornati si applicano solo ai progetti appena creati. Il codice per i progetti esistenti non viene aggiornato quando viene aggiornata l'estensione.

### <a name="update-vs-code-qdk-extension"></a>Aggiornare VS Code estensione QDK

1. Aggiornare l'estensione VS Code Quantum

    - Riavvia VS Code
    - Passare alla scheda **estensioni**
    - Selezionare l' **Microsoft Quantum Development Kit per Visual Studio Code** estensione
    - Ricarica l'estensione

2. Aggiornare i modelli di progetto Quantum:

   - Vai a **Visualizza**  ->  **riquadro comandi**
   - Selezionare **Q #: installare i modelli di progetto**
   - Dopo alcuni secondi dovrebbe essere visualizzata una finestra popup che conferma la corretta installazione di modelli di progetto

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, uso dello `dotnet` strumento da riga di comando

1. Aggiornare i modelli di progetto Quantum per .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```