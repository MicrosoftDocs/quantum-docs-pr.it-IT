---
title: Aggiornare Quantum Development Kit (QDK)
description: Descrive come aggiornare i progetti Q# e Microsoft Quantum Development Kit alla versione corrente.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 457083ea4756d64375834e5a276c2d91031138fe
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885142"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aggiornare Microsoft Quantum Development Kit (QDK)

Informazioni su come aggiornare Microsoft Quantum Development Kit (QDK) all'ultima versione.

In questo articolo si presuppone che il QDK sia già installato. Se si tratta della prima installazione, vedere la [guida all'installazione](xref:microsoft.quantum.install).

È consigliabile usare sempre la versione più recente del QDK. Seguire questa guida all'aggiornamento per eseguire l'aggiornamento alla versione più recente del QDK. Il processo è articolato in due parti:
1. Aggiornamento dei file e dei progetti Q# esistenti per allineare il codice all'eventuale sintassi aggiornata.
2. Aggiornamento del QDK stesso per l'ambiente di sviluppo scelto.

## <a name="updating-q-projects"></a>Aggiornamento dei progetti Q# 

Indipendentemente dal fatto che si usi C# o Python per ospitare le operazioni Q#, seguire queste istruzioni per aggiornare i progetti Q#.

1. In primo luogo, verificare di avere la versione più recente di [.NET Core SDK 3.1](https://dotnet.microsoft.com/download). Eseguire il comando seguente al prompt dei comandi:

    ```dotnetcli
    dotnet --version
    ```

    Verificare che l'output sia un valore pari o superiore a `3.1.100`. In caso contrario, installare la [versione più recente](https://dotnet.microsoft.com/download) e ripetere la verifica. Attenersi quindi alle istruzioni seguenti, a seconda della configurazione (Visual Studio, Visual Studio Code o direttamente dalla riga di comando).

### <a name="update-q-projects-in-visual-studio"></a>Aggiornare progetti Q# in Visual Studio
 
1. Eseguire l'aggiornamento alla versione più recente di Visual Studio 2019. Per le istruzioni, vedere [qui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019).
2. Aprire la soluzione in Visual Studio.
3. Nel menu selezionare **Compila** -> **Pulisci soluzione**.
4. In ognuno dei file con estensione csproj aggiornare il framework di destinazione a `netcoreapp3.1` o a `netstandard2.1` se si tratta di un progetto di libreria.
    Questo significa modificare le righe nel formato:

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    Per altre informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

5. In ognuno dei file con estensione csproj impostare l'SDK su `Microsoft.Quantum.Sdk`, come indicato nella riga seguente. Si noti che il numero di versione deve essere l'ultimo disponibile. Per determinarlo, esaminare le [note sulla versione](https://docs.microsoft.com/quantum/relnotes/).

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. Salvare e chiudere tutti i file della soluzione.

7. Selezionare **Strumenti** -> **Riga di comando** -> **Prompt dei comandi per gli sviluppatori**. In alternativa, è possibile usare la console di gestione pacchetti in Visual Studio.

8. Per ogni progetto nella soluzione eseguire il comando seguente per **rimuovere** questo pacchetto:

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   Se i progetti usano qualsiasi altro pacchetto Microsoft.Quantum o Microsoft.Azure.Quantum, ad esempio Microsoft.Quantum.Numerics, eseguire il comando **Aggiungi** per aggiornare la versione usata per tali pacchetti.

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. Chiudere il prompt dei comandi e selezionare **Compila** -> **Compila soluzione** (*non* selezionare Ricompila soluzione).

È ora possibile procedere con l'[aggiornamento dell'estensione Visual Studio QDK](#update-visual-studio-qdk-extension).


### <a name="update-q-projects-in-visual-studio-code"></a>Aggiornare progetti Q# in Visual Studio Code

1. In Visual Studio Code aprire la cartella contenente il progetto da aggiornare.
2. Selezionare **Terminale** -> **Nuovo terminale**.
3. Seguire le istruzioni per l'aggiornamento con la riga di comando riportate di seguito.

### <a name="update-q-projects-using-the-command-line"></a>Aggiornare i progetti Q# con la riga di comando

1. Passare alla cartella contenente il file di progetto principale.

2. Eseguire il comando seguente:

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. Determinare la versione corrente del QDK. Per trovarla, è possibile esaminare le [note sulla versione](https://docs.microsoft.com/quantum/relnotes/). La versione è indicata in un formato simile a `0.11.2006.207`.

4. In ognuno dei file `.csproj` seguire questa procedura:

    - Aggiornare il framework di destinazione a `netcoreapp3.1` o a `netstandard2.1` se si tratta di un progetto di libreria. Questo significa modificare le righe nel formato:

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        Per altre informazioni sulla specifica dei framework di destinazione, vedere [qui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).

    - Sostituire il riferimento all'SDK nella definizione del progetto. Assicurarsi che il numero di versione corrisponda al valore determinato nel **passaggio 3**.

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - Rimuovere il riferimento al pacchetto `Microsoft.Quantum.Development.Kit`, se presente, che verrà specificato nella voce seguente:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - Aggiornare la versione di tutti i pacchetti Microsoft Quantum alla versione rilasciata più di recente del QDK (determinata nel **passaggio 3**). I nomi dei pacchetti sono conformi ai criteri seguenti:

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        I riferimenti ai pacchetti hanno il formato seguente:

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - Salvare il file aggiornato.

    - Ripristinare le dipendenze del progetto eseguendo le operazioni seguenti:

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. Tornare alla cartella contenente il progetto principale ed eseguire:

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

Dopo aver completato l'aggiornamento dei progetti Q#, attenersi alle istruzioni seguenti per aggiornare il QDK stesso.

## <a name="updating-the-qdk"></a>Aggiornamento del QDK

Il processo per aggiornare il QDK varia a seconda del linguaggio di sviluppo e dell'ambiente usati.
Selezionare l'ambiente di sviluppo di seguito.

* [Python: aggiornare il pacchetto `qsharp`](#update-the-qsharp-python-package)
* [Notebook di Jupyter: aggiornare il kernel IQ#](#update-the-iq-jupyter-kernel)
* [Visual Studio: aggiornare l'estensione QDK](#update-visual-studio-qdk-extension)
* [VS Code: aggiornare l'estensione QDK](#update-vs-code-qdk-extension)
* [Riga di comando e C#: aggiornare i modelli di progetto](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a>Aggiornare il pacchetto Python `qsharp`

La procedura di aggiornamento varia a seconda che l'installazione originale sia stata eseguita con conda o con l'interfaccia della riga di comando .NET e pip.

#### <a name="update-using-conda-recommended"></a>[Aggiornamento con conda (scelta consigliata)](#tab/tabid-conda)

1. Attivare l'ambiente conda in cui è stato installato il pacchetto `qsharp` e quindi eseguire questo comando per aggiornarlo:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Eseguire il comando seguente dal percorso dei file `.qs`:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Aggiornamento con l'interfaccia della riga di comando .NET e pip (opzione avanzata)](#tab/tabid-dotnetcli)

1. Aggiornare il kernel `iqsharp` 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificare la versione di `iqsharp`

    ```dotnetcli
    dotnet iqsharp --version
    ```

    Dovrebbe venire visualizzato l'output seguente.

    ```
    iqsharp: 0.12.20070124
    Jupyter Core: 1.4.0.0
    ```

    Non importa se la versione di `iqsharp` in uso è superiore. Deve corrispondere all'[ultima versione](xref:microsoft.quantum.relnotes).

1. Aggiornare il pacchetto `qsharp`:

    ```
    pip install qsharp --upgrade
    ```

1. Verificare la versione di `qsharp`:

    ```
    pip show qsharp
    ```

    Dovrebbe venire visualizzato l'output seguente.

    ```
    Name: qsharp
    Version: 0.12.20070124
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. Eseguire il comando seguente dal percorso dei file `.qs`:

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

È ora possibile usare il pacchetto Python `qsharp` aggiornato per eseguire i programmi quantistici esistenti.

### <a name="update-the-iq-jupyter-kernel"></a>Aggiornare li kernel IQ# per Jupyter

La procedura di aggiornamento varia a seconda che l'installazione originale sia stata eseguita con conda o con l'interfaccia della riga di comando .NET e pip.

#### <a name="update-using-conda-recommended"></a>[Aggiornamento con conda (scelta consigliata)](#tab/tabid-conda)

1. Attivare l'ambiente conda in cui è stato installato il pacchetto `qsharp` e quindi eseguire questo comando per aggiornarlo:

    ```
    conda update -c quantum-engineering qsharp
    ```

1. Eseguire il comando seguente da una cella in ogni notebook di Jupyter Q# esistente:

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[Aggiornamento con l'interfaccia della riga di comando .NET e pip (opzione avanzata)](#tab/tabid-dotnetcli)

1. Aggiornare il pacchetto `Microsoft.Quantum.IQSharp`:

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Verificare la versione di `iqsharp`:

    ```dotnetcli
    dotnet iqsharp --version
    ```

    L'output dovrebbe essere simile al seguente:

    ```
    iqsharp: 0.12.20070124
    Jupyter Core: 1.4.0.0
    ```

    Non importa se la versione di `iqsharp` in uso è superiore. Deve corrispondere all'[ultima versione](xref:microsoft.quantum.relnotes).

1. Eseguire il comando seguente da una cella in ogni notebook di Jupyter Q# esistente:

    ```
    %workspace reload
    ```

***

È ora possibile usare il kernel IQ# aggiornato per eseguire i notebook Jupyter Q# esistenti.

### <a name="update-visual-studio-qdk-extension"></a>Aggiornare l'estensione Visual Studio QDK

1. Aggiornare l'estensione di Visual Studio per Q#

    - Visual Studio richiede di accettare gli aggiornamenti all'estensione [Microsoft Quantum Development Kit](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Accettare l'aggiornamento

    > [!NOTE]
    > I modelli di progetto vengono aggiornati con l'estensione. I modelli aggiornati si applicano solo ai progetti appena creati. Il codice per i progetti esistenti non viene aggiornato quando si aggiorna l'estensione.

### <a name="update-vs-code-qdk-extension"></a>Aggiornare l'estensione VS Code QDK

1. Aggiornare l'estensione VS Code per il calcolo quantistico

    - Riavviare VS Code
    - Passare alla scheda **Estensioni**
    - Selezionare l'estensione **Microsoft Quantum Development Kit for Visual Studio Code**
    - Ricaricare l'estensione

2. Aggiornare i modelli di progetto di calcolo quantistico:

   - Passare a **Visualizza** -> **Riquadro comandi**
   - Selezionare **Q#: Installa modelli di progetto**
   - Dopo alcuni secondi dovrebbe essere visualizzata una finestra popup che conferma la corretta installazione dei modelli di progetto

### <a name="c-using-the-dotnet-command-line-tool"></a>C#, con lo strumento da riga di comando `dotnet`

1. Aggiornare i modelli di progetto di calcolo quantistico per .NET

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
