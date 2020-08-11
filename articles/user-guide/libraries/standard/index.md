---
title: Introduzione alle librerie standard Q# Microsoft
description: Informazioni sulle librerie standard Q# Microsoft che definiscono le operazioni, le funzioni e i tipi di dati usati nei programmi quantistici.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868475"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Introduzione alle librerie standard Q#

Q# è supportato da una gamma di utili operazioni, funzioni e tipi definiti dall'utente diversi che comprendono le *librerie standard* Q#.
Il [pacchetto NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) installato durante la fase di [installazione e convalida](xref:microsoft.quantum.install) fornisce il compilatore Q# e parti della libreria standard che vengono implementati dai computer di destinazione.
Il [pacchetto `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) fornisce la parte delle librerie standard Q# portabili tra computer di destinazione.

I simboli definiti nelle librerie standard Q# sono definiti in modo molto più dettagliato e completo nella [documentazione relativa alle API](xref:microsoft.quantum.standardlibsintro).

Nelle sezioni seguenti verranno illustrate le funzionalità più importanti di ogni parte della libreria standard e verrà fornito un contesto sul modo in cui ogni funzionalità può essere usata nella pratica.
