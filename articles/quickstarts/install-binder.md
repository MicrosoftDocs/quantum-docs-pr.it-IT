---
title: Sviluppare con Q# e Binder
description: Informazioni su come creare un'applicazione Q# con Binder.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: quickstart
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f7e9b1ae67d6275ec7ba39ea411842dc537536c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856719"
---
# <a name="develop-with-no-locq-and-binder"></a>Sviluppare con Q# e Binder

È possibile usare Binder per eseguire e condividere i notebook di Jupyter online.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Usare Binder con gli esempi di Microsoft QDK

Per configurare automaticamente Binder per l'uso degli esempi di Microsoft QDK:

1. Aprire un browser ed eseguire https://aka.ms/try-qsharp.
1. Nella pagina di destinazione degli **esempi di Quantum Development Kit** fare clic sul **notebook Q#** per informazioni su come usare IQ# per scrivere notebook personalizzati di applicazioni quantistiche.

![Pagina di destinazione del QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>Usare Binder con notebook e repository personalizzati

Se in un repository GitHub sono già presenti notebook, è possibile configurare Binder per l'uso con il repository:

1. Assicurarsi che nella radice del repository sia presente un file denominato *Dockerfile*. Il file deve contenere almeno le righe seguenti:

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > È possibile verificare la versione più aggiornata di IQ# nelle [note sulla versione](xref:microsoft.quantum.relnotes).

    Per altre informazioni sulla creazione di un Dockerfile, vedere le [informazioni di riferimento su Dockerfile](https://docs.docker.com/engine/reference/builder/).

2. Aprire un browser e passare a [mybinder.org](https://mybinder.org).
3. Immettere il nome del repository sotto forma di **URL GitHub**, ad esempio *MyName/MyRepo* e quindi fare clic su **launch** (avvia).

![Modulo MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a>Passaggi successivi

Ora che è stato configurato l'ambiente Binder, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).
