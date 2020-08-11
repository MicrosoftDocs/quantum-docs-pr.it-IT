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
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="87fbf-103">Introduzione alle librerie standard Q#</span><span class="sxs-lookup"><span data-stu-id="87fbf-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="87fbf-104">Q# è supportato da una gamma di utili operazioni, funzioni e tipi definiti dall'utente diversi che comprendono le *librerie standard* Q#.</span><span class="sxs-lookup"><span data-stu-id="87fbf-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="87fbf-105">Il [pacchetto NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) installato durante la fase di [installazione e convalida](xref:microsoft.quantum.install) fornisce il compilatore Q# e parti della libreria standard che vengono implementati dai computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="87fbf-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="87fbf-106">Il [pacchetto `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) fornisce la parte delle librerie standard Q# portabili tra computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="87fbf-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="87fbf-107">I simboli definiti nelle librerie standard Q# sono definiti in modo molto più dettagliato e completo nella [documentazione relativa alle API](xref:microsoft.quantum.standardlibsintro).</span><span class="sxs-lookup"><span data-stu-id="87fbf-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="87fbf-108">Nelle sezioni seguenti verranno illustrate le funzionalità più importanti di ogni parte della libreria standard e verrà fornito un contesto sul modo in cui ogni funzionalità può essere usata nella pratica.</span><span class="sxs-lookup"><span data-stu-id="87fbf-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
