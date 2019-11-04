---
title: Informazioni su come aggiornare il Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463290"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a>Aggiornare il Microsoft Quantum Development Kit (QDK)

Informazioni su come aggiornare la Microsoft Quantum Development Kit (QDK) alla versione più recente.

In questo articolo si presuppone che QDK sia già installato. Se si sta installando per la prima volta, consultare la Guida all' [installazione](xref:microsoft.quantum.install).


## <a name="updating-q-projects"></a>Aggiornamento di progetti Q # 

1. Prima di tutto, installare la versione più recente del [.NET Core SDK 3,0](https://dotnet.microsoft.com/download) ed eseguire il comando seguente nel prompt dei comandi:
```bash
dotnet --version
```
 Verificare che l'output sia 3.0.100 o superiore, quindi seguire le istruzioni riportate di seguito in base alla configurazione.

### <a name="in-visual-studio"></a>In Visual Studio
 
 1. Eseguire l'aggiornamento alla versione più recente di Visual Studio 2019, vedere [qui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) per istruzioni
 2. Aprire la soluzione in Visual Studio
 3. Dal menu selezionare Compila > Pulisci soluzione 
 4. [Aggiornare il Framework di destinazione](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in ogni file con estensione csproj a netcoreapp 3.0 (o netstandard 2.1 se è un progetto di libreria)
 5. Salvare e chiudere tutti i file nella soluzione
 6. Selezionare Strumenti > riga di comando > Prompt dei comandi per gli sviluppatori
 7. Per ogni progetto nella soluzione, eseguire il comando seguente:
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
Se i progetti usano altri pacchetti Microsoft. Quantum, eseguire il comando anche per questi pacchetti. 
 8. Chiudere il prompt dei comandi e selezionare Compila > Compila soluzione ( *non* selezionare Ricompila soluzione perché la ricompilazione avrà inizialmente esito negativo)

### <a name="in-visual-studio-code"></a>In Visual Studio Code

1. In Visual Studio Code aprire la cartella contenente il progetto da aggiornare
1. Selezionare terminal > nuovo terminale
1. Seguire le istruzioni per l'aggiornamento tramite la riga di comando

### <a name="using-the-command-line"></a>Uso della riga di comando

1. Passare alla cartella contenente il file di progetto
2. Eseguire il comando seguente:
```bash
dotnet clean [project_name].csproj
```

3. [Aggiornare il Framework di destinazione](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in ogni file con estensione csproj a netcoreapp 3.0 (o netstandard 2.1 se è un progetto di libreria)
4. Eseguire il comando seguente:
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
Se il progetto usa altri pacchetti Microsoft. Quantum, eseguire il comando anche per questi pacchetti.

5. Salva e Chiudi tutti i file
6. Ripetere 1-4 per ogni dipendenza del progetto, quindi tornare alla cartella che contiene il progetto principale ed eseguire:
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a>Aggiornare IQ # per Python

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
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
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
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. Eseguire il comando seguente dal percorso dei file di `.qs`
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. È ora possibile usare la versione aggiornata di QDK per eseguire i programmi Quantum esistenti.

## <a name="update-iq-for-jupyter-notebooks"></a>Aggiornare IQ # per i notebook di Jupyter

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
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. Eseguire il comando seguente da una cella nel Jupyter Notebook:
    ```
    %workspace reload
    ```

1. È ora possibile aprire un notebook di Jupyter esistente ed eseguirlo con il QDK aggiornato.

## <a name="update-visual-studio-qdk-extension"></a>Aggiorna l'estensione QDK di Visual Studio

1. Aggiornare l'estensione di Visual Studio Q #

    - Visual Studio richiede di accettare gli aggiornamenti all' [estensione Quantum di Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Accetta l'aggiornamento

    > [!NOTE]
    > I modelli di progetto vengono aggiornati con l'estensione. I modelli aggiornati si applicano solo ai progetti appena creati. Il codice per i progetti esistenti non viene aggiornato quando viene aggiornata l'estensione.

## <a name="update-vs-code-qdk-extension"></a>Aggiornare VS Code estensione QDK

1. Aggiornare l'estensione VS Code Quantum

    - Riavvia VS Code
    - Passare alla scheda **estensioni**
    - Selezionare l' **Microsoft Quantum Development Kit per Visual Studio Code** estensione
    - Ricarica l'estensione

1. Aggiornare i modelli di progetto Quantum:

   - Passare a **Visualizza** -> **Riquadro comandi**
   - Selezionare **Q #: installare i modelli di progetto**

## <a name="c-using-the-dotnet-command-line-tool"></a>C#, uso dello strumento da riga di comando `dotnet`

1. Aggiornare i modelli di progetto Quantum per .NET

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a>Potrai anche

Ora che è stato aggiornato Quantum Development Kit nell'ambiente preferito, è possibile continuare a sviluppare ed eseguire i programmi Quantum. Se non è ancora stato scritto un programma, è possibile iniziare a usare [il primo programma Quantum](xref:microsoft.quantum.write-program).
