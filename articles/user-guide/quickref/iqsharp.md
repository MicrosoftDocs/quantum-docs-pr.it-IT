---
title: Comandi magic di IQ#
description: 'Pagina di riferimento rapido per i comandi IQ # Magic con i notebook Q # Jupyter'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431020"
---
# <a name="iq-magic-commands"></a>Comandi magic di IQ#

### <a name="general"></a>Generale

- `%config`: Ottiene o imposta le preferenze di configurazione.
- `%estimate`: Esegue una determinata funzione o operazione nel computer di destinazione QuantumSimulator.
- `%lsmagic`: Restituisce un elenco di tutti i comandi Magic attualmente disponibili.
- `%package`: Consente di caricare un pacchetto NuGet.
- `%performance`: Riporta le metriche delle prestazioni correnti per questo kernel.
- `%simulate`: Esegue una determinata funzione o operazione nel computer di destinazione QuantumSimulator.
- `%toffoli`: Esegue una determinata funzione o operazione nel computer di destinazione del simulatore ToffoliSimulator.
- `%who`: Fornisce azioni correlate all'area di lavoro corrente.
- `%workspace`: Restituisce un elenco di tutte le operazioni e le funzioni definite nella sessione corrente, in modo interattivo o caricato dall'area di lavoro corrente.

### <a name="chemistry"></a>Chimica

- `%chemistry.broombridge`: Carica e restituisce la rappresentazione di un problema di struttura elettronica Broombridge da un file con estensione YAML specificato.
- `%chemistry.encode`: Codifica un'Hamiltoniana fermione in un formato utilizzabile da Q #.
- `%chemistry.fh.add_terms`: Aggiunge termini a un'Hamiltoniana fermione.
- `%chemistry.fh.load`: Carica l'Hamiltoniana fermione per un problema di struttura elettronica. Il problema viene caricato da un file o passato come argomento.
- `%chemistry.inputstate.load`: Carica un problema di struttura elettronica Broombridge e restituisce lo stato di input selezionato.

### <a name="from-microsoftquantumkatas-package"></a>Dal pacchetto Microsoft. Quantum. Katas

- `%kata`: Esegue un singolo test e segnala se il test è stato superato correttamente.
- `%check_kata`: Verifica l'implementazione di riferimento per un singolo test di Kata.
    In particolare, sostituisce l'implementazione di riferimento per una singola attività nella cella e segnala se il test è stato superato correttamente.
