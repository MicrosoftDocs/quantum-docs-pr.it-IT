---
title: Contribuire a Microsoft Quantum Development Kit
description: Informazioni su come contribuire a Microsoft Quantum Development Kit e alla community di sviluppo quantistica.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 63c6f90a511c7bd14435b2e593af0d8615c18519
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904877"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Contribuire al Quantum Development Kit #

Quantum Development Kit è più di una raccolta di strumenti per la scrittura di programmi quantistici.
Fa parte di una vasta community di persone che esplorano il calcolo quantistico, eseguono ricerche sugli algoritmi quantistici, sviluppano nuove applicazioni per i dispositivi quantistici o che collaborano in qualsiasi altro modo per sfruttare al meglio la programmazione quantistica.
Come membro di tale community, Quantum Development Kit mira a offrire agli sviluppatori quantistici un'ampia gamma di background con le funzionalità necessarie.
I contributi degli utenti al Quantum Development Kit consentono di realizzare questo obiettivo migliorando gli strumenti usati da altri sviluppatori quantistici, il modo in cui tali strumenti vengono documentati e anche creando nuove caratteristiche e funzionalità che aiutano a rendere l'intera community di programmazione quantistica un luogo migliore per esplorare e creare.
Siamo molto grati per i contributi che riceviamo e per l'opportunità collaborare al miglioramento della community.

In questa guida vengono fornite alcune indicazioni su come fornire contributi utili per la community di programmazione quantistica.

## <a name="building-community"></a>Collaborare con la community ##

Il primo aspetto da considerare per i contributi è tenere sempre presente la community con cui si collabora.
Comportandosi in modo rispettoso e professionale verso i colleghi della community di programmazione quantistica e non solo, è possibile assicurarsi che l'impegno contribuisca a creare la community migliore e più accogliente possibile.

Nell'ambito di questi impegno, tutti i progetti del Quantum Development Kit hanno adottato il [Codice di comportamento Open Source di Microsoft](https://opensource.microsoft.com/codeofconduct/).
Per altre informazioni, vedere [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) (Domande frequenti sul Codice di comportamento Open Source di Microsoft) oppure contattare [opencode@microsoft.com](mailto:opencode@microsoft.com) per eventuali altre domande o commenti.

## <a name="what-kinds-of-contributions-help-the-community"></a>Quali tipi di contributi aiutano la community? ##

Esistono molti modi diversi per aiutare la community di programmazione quantistica attraverso i contributi.
In questa guida verranno illustrati tre modi particolarmente significativi per il Quantum Development Kit.
Tutti questi modi sono strategici ai fini della creazione di una community quantistica efficace.
Tuttavia, questo non è sicuramente un elenco esaustivo. Incoraggiamo gli utenti a esplorare altri modi per aiutare la community a sviluppare le promesse relative alla programmazione quantistica.

- **Segnalazione di bug.** Il primo passaggio per la correzione di bug e altri tipi di problemi consiste nell'identificarli. Se è stato rilevato un bug nel Quantum Development Kit, è possibile segnalarlo per consentirci di correggerlo e creare un set di strumenti migliore per la community di programmazione quantistica.
- **Miglioramento della documentazione.** Qualsiasi set di documentazione può sempre essere migliorato, esplorare ulteriori dettagli o essere reso più accessibile.
- **Contributi di codice.** Naturalmente, uno dei modi più diretti per contribuire consiste nell'aggiungere nuovo codice al Quantum Development Kit.

Questi diversi tipi di contributi sono estremamente preziosi e molto apprezzati.
Nella parte rimanente della guida verranno forniti consigli su come creare ogni tipo di contributo.

## <a name="where-do-contributions-go"></a>Dove vanno i contributi? ##

Quantum Development Kit include numerosi parti diverse che si combinano tra loro per realizzare una piattaforma per la scrittura di programmi quantistici.
Ognuna di queste parti diverse viene collocata in un repository differente, quindi uno degli aspetti più importanti da definire è il repository più adatto per ogni tipo di contributo.

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum): Esempi e strumenti che consentono di iniziare a usare Quantum Development Kit.
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): Librerie standard e specifiche di dominio per Quantum Development Kit.
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): Esercizi di programmazione autogestiti per l'apprendimento del calcolo quantistico e del linguaggio di programmazione Q#.
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): Compilatore Q#, l'estensione di Visual Studio e l'estensione di Visual Studio Code.
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): Framework di simulazione, generazione di codice e computer di destinazione di simulazione per Quantum Development Kit.
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): Kernel Jupyter e funzionalità host Python per Q#, oltre a immagini Docker per l'uso di IQ# negli ambienti cloud.
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): Codice sorgente per la documentazione pubblicata in https://docs.microsoft.com/quantum.

> [!NOTE]
> Purtroppo non è possibile accettare contributi per codice e documentazione nel repository [**Microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) in questo momento, ma sono sempre molto apprezzate le segnalazioni di bug.

Sono anche disponibili alcuni altri repository più specializzati dedicati a eventi diversi o a funzionalità ausiliarie correlate a Quantum Development Kit.

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): Supporto della formattazione LaTeX per la sintassi Q#.
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019): Notebook IQ# notebook per l'esercitazione Deutsch-Jozsa fornita nel workshop interno del 2019.

## <a name="next-steps"></a>Passaggi successivi ##

Grazie per la partecipazione alla community di Quantum Development Kit. I contributi sono molto apprezzati.
Per altre informazioni sui contributi, continuare con una delle guide seguenti.

> [!div class="nextstepaction"]
> [Informazioni su come segnalare i bug](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [Informazioni su come contribuire alla documentazione](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [Informazioni su come aprire richieste pull](xref:microsoft.quantum.contributing.pulls)
