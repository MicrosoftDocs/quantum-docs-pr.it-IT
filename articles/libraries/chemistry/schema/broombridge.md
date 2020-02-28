---
title: Broombridge-schema di chimica quantistica
description: Panoramica dello schema di chimica quantistica Broombridge, usato per modellare i problemi di chimica del mondo reale con la Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907818"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Schema di chimica quantistica Broombridge # 

Un potente software di chimica computazionale come [nwchem](http://www.nwchem-sw.org/) consente di modellare un'ampia gamma di problemi di chimica reali. Per accedere ai modelli molecolari NWChem con la libreria Microsoft Quantum Chemistry, viene usato uno schema basato su [YAML](https://en.wikipedia.org/wiki/YAML)che viene chiamato **Broombridge**. Il nome è stato scelto in riferimento a un [punto](https://en.wikipedia.org/wiki/Broom_Bridge) di riferimento che in alcuni cerchi viene celebrato come un luogo di nascita di hamiltonians. 

[Nwchem](https://github.com/nwchemgit/nwchem) è un progetto open source concesso in licenza con la licenza ECL (permissive Educational Community License 2,0). Broombridge è uno schema open source specificato [qui](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) e che include una [definizione](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) che segue la [RFC 2119](https://tools.ietf.org/html/rfc2119) e [lo script validator](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) concesso in licenza con la licenza MIT. 

Essendo basato su YAML, Broombridge è un modo strutturato, leggibile e modificabile per la rappresentazione di problemi di struttura elettronica. In particolare, è possibile rappresentare i dati seguenti: 
- Fermioniche hamiltonians può essere rappresentato usando integrali a uno e due elettroni. 
- Gli Stati di base e entusiasta possono essere presentati usando le sequenze di creazione.
- È possibile specificare i limiti superiore e inferiore dei livelli di energia.

Il formato dei dati può essere generato da NWChem con facilità: è disponibile un'ampia gamma di metodi che variano da un'installazione completa di NWChem per l'esecuzione di deck di chimica come quelli forniti [qui](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) e output Broombridge come parte dell'esecuzione, su un'immagine Docker di nwchem, che può essere usata anche per generare Broombridge da Deck di chimica. Infine, un metodo visivo per iniziare rapidamente a usare la chimica computazionale senza dover installare alcun software chimico viene fornito dall'interfaccia [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) a nwchem. 

A livello generale, l'interazione tra NWChem e il Microsoft Quantum Development Kit può essere visualizzata come segue: ![lo stack di chimica](~/media/broombridge.png) la casella ombreggiata blu rappresenta lo schema Broombridge, le varie caselle ombreggiate grigio rappresentano altre rappresentazioni di dati interne che sono state scelte per rappresentare ed elaborare algoritmi quantistici per la chimica computazionale basata su problemi di chimica reali. 

[Qui](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)sono disponibili più rappresentazioni chimiche definite usando lo schema Broombridge.
