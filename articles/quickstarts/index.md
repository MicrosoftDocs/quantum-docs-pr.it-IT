---
title: Configurazione del kit di sviluppo Microsoft Quantum (QDK)
description: Informazioni su come configurare il kit di sviluppo Microsoft Quantum per ambienti diversi.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834483"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Configurazione del kit di sviluppo Microsoft Quantum (QDK)

Informazioni su come configurare il kit di sviluppo Microsoft Quantum (QDK) per l'ambiente, per iniziare a sviluppare con la programmazione quantistica. Contenuto del QDK:

- Linguaggio di programmazione Q#
- Set di librerie che estrapolano funzionalità complesse in Q#
- API per linguaggi Python e .NET (C#, F# e VB.NET) per l'esecuzione di programmi quantistici scritti in Q#
- Strumenti per facilitare lo sviluppo

I programmi Q# possono essere eseguiti come applicazioni autonome usando Visual Studio Code o Visual Studio, tramite notebook di Jupyter con il kernel Jupyter IQ# oppure abbinati a un programma host scritto in Python o in un linguaggio .NET (C#, F#). È anche possibile eseguire i programmi Q# online usando [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) o [Docker](#use-the-qdk-with-docker). 

## <a name="options-for-setting-up-the-qdk"></a>Opzioni per la configurazione del QDK

È possibile usare il QDK in tre modi:

- [Installare il QDK in locale](#install-the-qdk-locally)
- [Usare il QDK online](#use-the-qdk-online)
- [Usare un'immagine Docker del QDK](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>Installare il QDK in locale

È possibile sviluppare codice Q# nella maggior parte degli IDE preferiti, nonché integrare Q# con altri linguaggi, ad esempio Python e .NET (C#, F#).

|&nbsp; | **VS Code<br>(2019 o versione successiva)**| **Visual Studio<br>(2019 o versione successiva)** | **Jupyter Notebook** | **Riga di comando**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**Sistema operativo** |Windows, macOS, Linux |Solo Windows |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**Q# autonomo** |<br>[Installazione](xref:microsoft.quantum.install.standalone) |<br> [Installazione](xref:microsoft.quantum.install.standalone)  |<br> [Installazione](xref:microsoft.quantum.install.jupyter) |<br>[Installazione](xref:microsoft.quantum.install.standalone)|
|**Q# e Python** |[Installazione](xref:microsoft.quantum.install.python) |[Installazione](xref:microsoft.quantum.install.python) |[Installazione](xref:microsoft.quantum.install.jupyter) |[Installazione](xref:microsoft.quantum.install.python) |
|**Q# e .NET (C#, F#)**|[Installazione](xref:microsoft.quantum.install.cs) |[Installazione](xref:microsoft.quantum.install.cs)|&#10006; |[Installazione](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a>Usare il QDK online

È anche possibile sviluppare codice Q# senza installare niente in locale con queste opzioni:

|Risorsa|Vantaggi|Limitazioni|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|Un ambiente di sviluppo online avanzato  |Richiede una sottoscrizione e un piano di Azure |
|[**Binder**](xref:microsoft.quantum.install.binder) | Esperienza gratuita di notebook online |Nessuna persistenza |

## <a name="use-the-qdk-with-docker"></a>Usare il QDK con Docker

È possibile usare l'immagine Docker del QDK nell'installazione locale di Docker o nel cloud tramite qualsiasi servizio che supporti immagini Docker, ad esempio Istanze di Azure Container.

È possibile scaricare l'immagine Docker IQ# da https://github.com/microsoft/iqsharp/#using-iq-as-a-container. 

È anche possibile usare Docker con un contenitore di sviluppo remoto di Visual Studio Code per definire rapidamente gli ambienti di sviluppo. Per altre informazioni sui contenitori di sviluppo di VS Code, vedere https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Passaggi successivi

I flussi di lavoro per ognuna di queste configurazioni vengono descritti e confrontati in [Modalità di esecuzione di programmi Q#](xref:microsoft.quantum.guide.host-programs).
