---
title: Applicazioni di esempio di chimica quantistica
description: Esplorare le applicazioni di esempio della libreria di chimica quantistica Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273617"
---
# <a name="quantum-chemistry-examples"></a>Esempi di chimica quantistica

Nei concetti di chimica quantistica sono state create manualmente le hamiltoniane di particelle fermioniche di esempio. Gli algoritmi di simulazione chimica descritti in [Simulazione della dinamica hamiltoniana](xref:microsoft.quantum.libraries.standard.algorithms) verranno ora combinati con la [stima della fase quantistica](xref:microsoft.quantum.libraries.characterization) nella libreria canonica. Questa combinazione permette di ottenere stime dei livelli di energia nella molecola rappresentata e questa costituisce una delle applicazioni chiave della chimica quantistica in un computer quantistico. 

Invece di specificare i termini dell'hamiltoniana uno alla volta, verranno usati alcuni esempi che consentono di eseguire esperimenti di chimica quantistica su larga scala. Si inizierà con esempi che caricano un'hamiltoniana chimica codificata nello [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

Per le molecole che sono troppo grandi per la simulazione nel [simulatore di stati completo](xref:microsoft.quantum.machines.full-state-simulator), è comunque possibile eseguire interessanti esperimenti scientifici. È ad esempio possibile valutare comunque i costi di simulazioni chimiche di grandi dimensioni in termini di risorse impostando come destinazione il [simulatore di tracce](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

A questo punto verranno usati alcuni degli esempi forniti per illustrare le interessanti applicazioni della libreria di simulazione chimica.