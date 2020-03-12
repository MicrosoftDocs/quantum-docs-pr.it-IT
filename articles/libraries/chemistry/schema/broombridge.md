---
title: Schema di chimica quantistica Broombridge
description: Panoramica dello schema di chimica quantistica Broombridge, usato per modellare i problemi di chimica del mondo reale con la Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022532"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Schema di chimica quantistica Broombridge # 

Un potente software di chimica computazionale come [nwchem](http://www.nwchem-sw.org/) consente di modellare un'ampia gamma di problemi di chimica reali. Per accedere ai modelli molecolari NWChem con la libreria Microsoft Quantum Chemistry, si usa uno schema basato su [YAML](https://en.wikipedia.org/wiki/YAML)denominato **Broombridge**. Il nome è stato scelto in riferimento a un [punto](https://en.wikipedia.org/wiki/Broom_Bridge) di riferimento che in alcuni cerchi viene celebrato come un luogo di nascita di hamiltonians. 

[Nwchem](https://github.com/nwchemgit/nwchem) è un progetto open source concesso in licenza con la licenza ECL (permissive Educational Community License 2,0). Lo [schema di chimica quantistica Broombridge](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)è uno schema open source che include una [definizione](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) che segue [RFC 2119](https://tools.ietf.org/html/rfc2119) e uno [script validator](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) concesso in licenza con la licenza MIT. 

Essendo basato su YAML, Broombridge è un modo strutturato, leggibile e modificabile per la rappresentazione di problemi di struttura elettronica. In particolare, è possibile rappresentare i dati seguenti:
- Fermioniche hamiltonians può essere rappresentato usando integrali a uno e due elettroni.
- Gli Stati di base e entusiasta possono essere presentati usando le sequenze di creazione.
- È possibile specificare i limiti superiore e inferiore dei livelli di energia.

I dati possono essere generati da NWChem usando diversi metodi, ad esempio l'uso di un'installazione completa di NWChem per eseguire i deck di chimica (ad esempio quelli forniti nella [libreria nwchem](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) che restituiscono Broombridge come parte dell'esecuzione) o un'immagine Docker di nwchem che può essere usata anche per generare Broombridge da Deck di chimica. Per iniziare rapidamente a usare la chimica computazionale senza dover installare software di chimica, è possibile usare l'interfaccia visiva per NWChem fornita dalle [frecce EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem).

A livello generale, l'interazione tra NWChem e il Microsoft Quantum Development Kit può essere visualizzata come segue: ![lo stack di chimica](~/media/broombridge.png) la casella ombreggiata blu rappresenta lo schema Broombridge, le varie caselle ombreggiate grigio rappresentano altre rappresentazioni di dati interne che sono state scelte per rappresentare ed elaborare algoritmi quantistici per la chimica computazionale basata su problemi di chimica reali.

La cartella [integrale/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) nel repository di esempi di Quantum Development Kit contiene più rappresentazioni chimiche definite mediante lo schema Broombridge.
