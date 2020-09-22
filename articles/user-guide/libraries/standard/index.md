---
title: Introduzione alle librerie standard Q# Microsoft
description: Informazioni sulle librerie standard Q# Microsoft che definiscono le operazioni, le funzioni e i tipi di dati usati nei programmi quantistici.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 63709015a12a7f972a676018970143ca163e92d0
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836013"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Introduzione alle librerie standard Q#

Q# è supportato da una gamma di utili operazioni, funzioni e tipi definiti dall'utente diversi che comprendono le *librerie standard* Q#.
Il [pacchetto NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) installato durante la fase di [installazione e convalida](xref:microsoft.quantum.install) fornisce il compilatore Q# e parti della libreria standard che vengono implementati dai computer di destinazione.
Il [pacchetto `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) fornisce la parte delle librerie standard Q# portabili tra computer di destinazione.

I simboli definiti nelle librerie standard Q# sono definiti in modo molto più dettagliato e completo nella [documentazione relativa alle API](xref:microsoft.quantum.apiref-intro).

Nelle sezioni seguenti verranno illustrate le funzionalità più importanti di ogni parte della libreria standard e verrà fornito un contesto sul modo in cui ogni funzionalità può essere usata nella pratica.
