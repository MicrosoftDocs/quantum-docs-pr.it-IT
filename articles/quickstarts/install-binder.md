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
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="0cc8d-103">Sviluppare con Q# e Binder</span><span class="sxs-lookup"><span data-stu-id="0cc8d-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="0cc8d-104">È possibile usare Binder per eseguire e condividere i notebook di Jupyter online.</span><span class="sxs-lookup"><span data-stu-id="0cc8d-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="0cc8d-105">Usare Binder con gli esempi di Microsoft QDK</span><span class="sxs-lookup"><span data-stu-id="0cc8d-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="0cc8d-106">Per configurare automaticamente Binder per l'uso degli esempi di Microsoft QDK:</span><span class="sxs-lookup"><span data-stu-id="0cc8d-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="0cc8d-107">Aprire un browser ed eseguire https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="0cc8d-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="0cc8d-108">Nella pagina di destinazione degli **esempi di Quantum Development Kit** fare clic sul **notebook Q#** per informazioni su come usare IQ# per scrivere notebook personalizzati di applicazioni quantistiche.</span><span class="sxs-lookup"><span data-stu-id="0cc8d-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![Pagina di destinazione del QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="0cc8d-110">Usare Binder con notebook e repository personalizzati</span><span class="sxs-lookup"><span data-stu-id="0cc8d-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="0cc8d-111">Se in un repository GitHub sono già presenti notebook, è possibile configurare Binder per l'uso con il repository:</span><span class="sxs-lookup"><span data-stu-id="0cc8d-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="0cc8d-112">Assicurarsi che nella radice del repository sia presente un file denominato *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="0cc8d-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="0cc8d-113">Il file deve contenere almeno le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cc8d-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="0cc8d-114">È possibile verificare la versione più aggiornata di IQ# nelle [note sulla versione](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="0cc8d-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="0cc8d-115">Per altre informazioni sulla creazione di un Dockerfile, vedere le [informazioni di riferimento su Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="0cc8d-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="0cc8d-116">Aprire un browser e passare a [mybinder.org](https://mybinder.org).</span><span class="sxs-lookup"><span data-stu-id="0cc8d-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="0cc8d-117">Immettere il nome del repository sotto forma di **URL GitHub**, ad esempio *MyName/MyRepo* e quindi fare clic su **launch** (avvia).</span><span class="sxs-lookup"><span data-stu-id="0cc8d-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![Modulo MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="0cc8d-119">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0cc8d-119">Next steps</span></span>

<span data-ttu-id="0cc8d-120">Ora che è stato configurato l'ambiente Binder, è possibile scrivere ed eseguire [il primo programma quantistico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="0cc8d-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
