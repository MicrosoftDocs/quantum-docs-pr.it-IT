---
title: Applicazioni di esempio di chimica quantistica
description: Esplorare le applicazioni di esempio della libreria di chimica quantistica Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: a0bc79c7fb41069ee7865dbf2f1cfd7851fda32d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869291"
---
# <a name="quantum-chemistry-examples"></a>Esempi di chimica quantistica

Nei concetti di chimica quantistica sono state create manualmente le hamiltoniane di particelle fermioniche di esempio. Gli algoritmi di simulazione chimica descritti in [Simulazione della dinamica hamiltoniana](xref:microsoft.quantum.libraries.standard.algorithms) verranno ora combinati con la [stima della fase quantistica](xref:microsoft.quantum.libraries.characterization) nella libreria canonica. Questa combinazione permette di ottenere stime dei livelli di energia nella molecola rappresentata e questa costituisce una delle applicazioni chiave della chimica quantistica in un computer quantistico. 

Invece di specificare i termini dell'hamiltoniana uno alla volta, verranno usati alcuni esempi che consentono di eseguire esperimenti di chimica quantistica su larga scala. Si inizierà con esempi che caricano un'hamiltoniana chimica codificata nello [schema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

Per le molecole che sono troppo grandi per la simulazione nel [simulatore di stati completo](xref:microsoft.quantum.machines.full-state-simulator), è comunque possibile eseguire interessanti esperimenti scientifici. È ad esempio possibile valutare comunque i costi di simulazioni chimiche di grandi dimensioni in termini di risorse impostando come destinazione il [simulatore di tracce](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

A questo punto verranno usati alcuni degli esempi forniti per illustrare le interessanti applicazioni della libreria di simulazione chimica.
