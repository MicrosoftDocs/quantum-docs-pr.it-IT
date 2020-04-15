---
title: Introduzione al pacchetto di apprendimento automatico quantistico | Microsoft Docs
description: Introduzione al pacchetto di apprendimento automatico quantistico
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907852"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Introduzione alla libreria di apprendimento automatico quantistico

La libreria di apprendimento automatico quantistico è un'API, scritta in Q#, che consente di eseguire esperimenti di apprendimento automatico ibrido quantistico/classico. Con la libreria è possibile:

- Caricare dati personalizzati per la classificazione con simulatori quantistici

- Usare esempi ed esercitazioni per avvicinarsi al campo dell'apprendimento automatico quantistico

Le prestazioni previste sono decisamente inferiori rispetto a quelle degli attuali framework di apprendimento automatico classico. Tenere presente infatti che gli esperimenti vengono eseguiti sulla simulazione di un dispositivo quantistico che è già di per sé oneroso dal punto di vista del calcolo.

Lo scopo di questa documentazione è:

- Offrire una breve introduzione agli strumenti di apprendimento automatico (scritti in Q\#) per l'apprendimento ibrido quantistico/classico.
- Introdurre i concetti di apprendimento automatico e, in particolare, la loro realizzazione in classificatori incentrati sul circuito quantistico (noti anche come classificatori sequenziali quantistici).
- Fornire un set di esercitazioni sulle nozioni di base per iniziare a usare gli strumenti forniti dalla libreria.
- Illustrare i metodi di training e convalida per questi classificatori e spiegare in che modo vengono convertiti in specifiche operazioni Q\# fornite dalla libreria.

Il modello implementato in questa libreria è basato sullo schema di training classico quantistico illustrato nel documento [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633).
