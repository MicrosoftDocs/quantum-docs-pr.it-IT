---
title: Uso di Q# librerie aggiuntive
description: Informazioni su come aggiungere Q# librerie aggiuntive alle applicazioni Quantum.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869580"
---
# <a name="using-additional-no-locq-libraries"></a>Uso di Q# librerie aggiuntive

Quantum Development Kit fornisce funzionalità aggiuntive specifiche del dominio tramite i _pacchetti NuGet_ che è possibile aggiungere ai Q# progetti.

| Q#Libreria  | Pacchetto NuGet | Note |
|---------|---------|--------|
| [Q#libreria standard](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. Quantum. standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Inclusa per impostazione predefinita |
| [Libreria di chimica quantistica](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Libreria per il calcolo numerico quantistico](xref:microsoft.quantum.numerics.intro) | [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Libreria di apprendimento automatico quantistico](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Una volta installato Quantum Development Kit per l'uso con l'ambiente preferito e il linguaggio host, è possibile aggiungere facilmente librerie a singoli Q# progetti senza ulteriori installazioni.

> [!NOTE]
> Alcune Q# librerie possono funzionare correttamente con strumenti aggiuntivi che funzionano insieme ai Q# programmi o che si integrano con le applicazioni host.
> Ad esempio, le [istruzioni di installazione della libreria di chimica](xref:microsoft.quantum.chemistry.concepts.installation) descrivono come usare il [pacchetto **Microsoft. Quantum. Chemistry** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) con la piattaforma chimica computazionale nwchem e come installare gli `qdk-chem` strumenti da riga di comando per l'utilizzo di dati di chimica quantistica.

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[Q#applicazioni da riga di comando o interoperabilità .NET](#tab/tabid-csproj)

**Riga di comando o Visual Studio Code:** Usando la riga di comando autonomamente o dall'interno di Visual Studio Code, è possibile usare il `dotnet` comando per aggiungere un riferimento al pacchetto NuGet al progetto.
Ad esempio, per aggiungere il pacchetto [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , eseguire il comando seguente:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Se si usa Visual Studio 2019 o versione successiva, è possibile aggiungere altri Q# pacchetti usando Gestione pacchetti NuGet.
Per caricare un pacchetto: 
1. Con un progetto aperto in Visual Studio, scegliere **Gestisci pacchetti NuGet** dal menu **progetto** .

2. Fare clic su **Sfoglia**, selezionare **Includi versione preliminare** e cercare il nome del pacchetto "Microsoft. Quantum. Numerics". In questo elenco vengono elencati i pacchetti disponibili per il download.

3. Passare il mouse su **Microsoft. Quantum. Numerics** e fare clic sulla freccia rivolta verso il basso a destra del numero di versione per installare il pacchetto Numerics.

Per ulteriori informazioni, vedere la [Guida dell'interfaccia utente di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-ui).

In alternativa, è possibile usare la console di gestione pacchetti per aggiungere la libreria Numerics al progetto tramite l'interfaccia della riga di comando.

![Usare la console di gestione pacchetti dalla riga di comando](~/media/vs2017-nuget-console-menu.png)

Dalla console di gestione pacchetti eseguire le operazioni seguenti:

```
Install-Package Microsoft.Quantum.Numerics
```

Per ulteriori informazioni, vedere la [Guida della console di gestione pacchetti](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="ino-locq-notebooks"></a>[I Q# notebook](#tab/tabid-notebook)

È possibile rendere disponibili pacchetti aggiuntivi per l'uso in un Q# notebook di i, usando il [ `%package` comando Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).
Ad esempio, per aggiungere il pacchetto [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) da usare in un Q# notebook i, eseguire il comando seguente in una cella del notebook:

```
%package Microsoft.Quantum.Numerics
```

Dopo questo comando, il pacchetto è disponibile per tutte le celle all'interno del notebook.
Per rendere il pacchetto disponibile dal Q# codice nell'area di lavoro corrente, ricaricare l'area di lavoro dopo aver aggiunto il pacchetto:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Interoperabilità di Python](#tab/tabid-python)


È possibile rendere disponibili pacchetti aggiuntivi da usare in un programma host Python usando il [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) metodo.
Ad esempio, per aggiungere il pacchetto [**Microsoft. Quantum. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) da usare in un Q# notebook i, eseguire il codice Python seguente:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Seguendo questo comando, il pacchetto verrà reso disponibile per qualsiasi Q# codice compilato usando `qsharp.compile` .
Per rendere il pacchetto disponibile dal Q# codice nell'area di lavoro corrente, ricaricare l'area di lavoro dopo aver aggiunto il pacchetto:

```python
qsharp.reload()
```

***
