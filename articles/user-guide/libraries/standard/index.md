---
title: Introduzione alle librerie standard di Microsoft Q#
description: Informazioni sulle librerie standard di Microsoft Q# che definiscono le operazioni, le funzioni e i tipi di dati usati nei programmi quantistici.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: ab069c496d89a57f979732da6ccdfbe673b79726
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870584"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Introduzione alle librerie standard Q#

Q# è supportato da una gamma di utili operazioni, funzioni e tipi definiti dall'utente diversi che comprendono le *librerie standard* Q#.
Il [pacchetto NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) installato durante la fase di [installazione e convalida](xref:microsoft.quantum.install) fornisce il compilatore Q# e parti della libreria standard che vengono implementati dai computer di destinazione.
Il [pacchetto `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) fornisce la parte delle librerie standard Q# portabili tra computer di destinazione.

I simboli definiti nelle librerie standard Q# sono definiti in modo molto più dettagliato e completo nella [documentazione relativa alle API](xref:microsoft.quantum.standardlibsintro).

Nelle sezioni seguenti verranno illustrate le funzionalità più importanti di ogni parte della libreria standard e verrà fornito un contesto sul modo in cui ogni funzionalità può essere usata nella pratica.
