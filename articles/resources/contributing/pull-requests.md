---
title: Apertura delle richieste pull
description: Informazioni su come inviare una richiesta pull di GitHub quando si è pronti per contribuire al codice o alla documentazione per la Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: 82af3b5123588cc06882f746ffcb0402ad3f0f2e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274844"
---
# <a name="opening-pull-requests"></a>Apertura di richieste pull #

Tutta la documentazione relativa a Quantum Development Kit viene gestita con il sistema di controllo della versione di git tramite l'uso di diversi repository ospitati in GitHub.
L'uso di git e GitHub insieme semplifica la collaborazione in Quantum Development Kit.
In particolare, tutti i repository git possono essere clonati o biforcati per creare una copia completamente indipendente del repository.
In questo modo è possibile lavorare sul proprio contributo con gli strumenti e con i ritmi preferiti.

Quando si è pronti, è possibile inviare una richiesta per includere il contributo nei repository, usando la funzionalità delle _richieste pull_ di GitHub.
La pagina per ogni richiesta pull include i dettagli di tutte le modifiche apportate al contributo, un elenco di commenti sul contributo e un set di strumenti di revisione che possono essere usati da altri membri della community per fornire commenti e suggerimenti.

> [!NOTE]
> Anche se un'esercitazione completa su git esula dall'ambito di questa guida, è possibile suggerire i collegamenti seguenti per altre risorse sull'apprendimento di git:
>
> - [Informazioni su git](https://www.atlassian.com/git): un set di esercitazioni git da Atlassian.
> - [Controllo della versione in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): Guida su come usare Visual Studio Code come GUI per git.
> - [Lab Learning di GitHub](https://lab.github.com/): un set di corsi online per l'uso di Git, GitHub e delle tecnologie correlate.
> - [Visualizzazione di git](https://git-school.github.io/visualizing-git/): strumento interattivo per visualizzare il modo in cui i comandi Git cambiano lo stato di un repository.
> - [Controllo della versione con git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): esercitazione git orientata al calcolo scientifico.
> - [Informazioni sulle diramazioni di git](https://learngitbranching.js.org/): un set interattivo di diramazioni e ribasare i puzzle per apprendere le nuove funzionalità di git.

## <a name="what-is-a-pull-request"></a>Che cos'è una richiesta pull? ##

Detto quanto sopra, è utile richiedere alcuni istanti per indicare **la richiesta di**pull.
Quando si usa Git, tutte le modifiche vengono rappresentate come _commit_ che descrivono il modo in cui tali modifiche sono correlate allo stato del repository prima di tali modifiche.
Spesso si disegnano diagrammi in cui i commit vengono disegnati come cerchi con frecce dei commit precedenti.

Si supponga di avere avviato un contributo in un _ramo_ denominato `feature` .
Il fork di **Microsoft/Quantum** potrebbe avere un aspetto simile al seguente:

![Un ramo di lavoro in GitHub](~/media/git-workflow-step0.png)

Se si apportano le modifiche nel repository locale, è possibile effettuare il _pull_ delle modifiche da un altro repository nel proprio per recuperare le modifiche apportate a upstream.

![Pull e Unione di modifiche da un repository upstream](~/media/git-workflow-step1.png)

Le richieste pull funzionano allo stesso modo, ma in senso inverso: quando si apre una richiesta pull, si chiede al repository upstream di effettuare il pull del contributo in.

![Richiesta di eseguire il pull delle modifiche nel repository originale](~/media/git-workflow-step2.png)

Quando si apre una richiesta pull a uno dei repository, GitHub offrirà agli altri utenti della community la possibilità di visualizzare un riepilogo delle modifiche apportate, di commentarle e di fornire suggerimenti su come contribuire a migliorare ulteriormente il contributo.

![Screenshot di una richiesta pull in GitHub](~/media/pull-request-header.png)

L'uso di questo processo consente di usare la funzionalità GitHub per migliorare i contributi e mantenere un prodotto di alta qualità per la community di programmazione quantistica.

## <a name="how-to-make-a-pull-request"></a>Come effettuare una richiesta pull ##

Esistono due modi principali per effettuare una richiesta pull.  
Per le piccole modifiche che influiscono solo su un singolo file, è possibile usare l'interfaccia Web GitHub per creare una richiesta pull interamente online. È sufficiente passare al file che si desidera modificare e utilizzare l'icona di modifica.  
Per i contributi più complessi, è spesso più semplice clonare il repository nel computer locale per prepararsi prima di tutto a una richiesta pull.

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a>Passaggi successivi ##

Congratulazioni per aver usato git per aiutare la community di Quantum Development Kit.
Per altre informazioni su come contribuire al codice, continuare con la guida seguente.

> [!div class="nextstepaction"]
> [Informazioni su come contribuire al codice](xref:microsoft.quantum.contributing.code)
