---
title: Comandi magic di IQ#
description: 'Pagina di riferimento rapido per i comandi IQ # Magic con i notebook Q # Jupyter'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 2fb542df8723fa437c82b4a1dfada77e22c1d6e4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870542"
---
# <a name="iq-magic-commands"></a>Comandi magic di IQ#

### <a name="general"></a>Generale

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Consente di impostare o eseguire query sulle opzioni di configurazione.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Esegue una determinata funzione o operazione nel computer di destinazione ResourcesEstimator.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Restituisce un elenco di tutti i comandi Magic attualmente disponibili.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Consente di caricare un pacchetto NuGet.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Riporta le metriche delle prestazioni correnti per questo kernel.
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Esegue una determinata funzione o operazione nel computer di destinazione QuantumSimulator.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Esegue una determinata funzione o operazione nel computer di destinazione ToffoliSimulator.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Elenca le operazioni Q # disponibili nella sessione corrente.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Fornisce azioni correlate all'area di lavoro corrente.

### <a name="azure-quantum-integration"></a>Integrazione di Azure Quantum

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Si connette a un'area di lavoro di Azure Quantum o Visualizza lo stato corrente della connessione.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Esegue un processo in un'area di lavoro Quantum di Azure.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Visualizza un elenco di processi nell'area di lavoro Quantum di Azure corrente.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Visualizza i risultati per un processo nell'area di lavoro Quantum di Azure corrente.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Visualizza lo stato di un processo nell'area di lavoro Quantum di Azure corrente.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Invia un processo a un'area di lavoro Quantum di Azure.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Imposta o Visualizza la destinazione di esecuzione attiva per l'invio di processi Q # in un'area di lavoro Quantum di Azure.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Chimica (dal pacchetto Microsoft. Quantum. Chemistry)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Carica e restituisce la rappresentazione di un problema di struttura elettronica Broombridge da un file con estensione YAML specificato.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Codifica un'Hamiltoniana fermione in un formato utilizzabile da Q #.
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Aggiunge termini a un'Hamiltoniana fermione.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Carica l'Hamiltoniana fermione per un problema di struttura elettronica. Il problema viene caricato da un file o passato come argomento.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Carica un problema di struttura elettronica Broombridge e restituisce lo stato di input selezionato.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (dal pacchetto Microsoft. Quantum. Katas)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Esegue un singolo test e segnala se il test è stato superato correttamente.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Verifica l'implementazione di riferimento per un singolo test di Kata.
    In particolare, sostituisce l'implementazione di riferimento per una singola attività nella cella e segnala se il test è stato superato correttamente.
