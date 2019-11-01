---
uid: microsoft.quantum.standardlibsintro
title: Libreria standard Q# per il calcolo quantistico Microsoft
description: Documentazione di riferimento per la libreria standard Q# per il calcolo quantistico Microsoft
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999094"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="3d69d-103">Librerie standard Q#</span><span class="sxs-lookup"><span data-stu-id="3d69d-103">Q# standard libraries</span></span> #

<span data-ttu-id="3d69d-104">Q# è supportato da una gamma di utili operazioni, funzioni e tipi definiti dall'utente diversi che comprendono la *libreria standard* Q#.</span><span class="sxs-lookup"><span data-stu-id="3d69d-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="3d69d-105">La libreria standard Q# è suddivisa in due parti principali:</span><span class="sxs-lookup"><span data-stu-id="3d69d-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="3d69d-106">**Preludio**: operazioni e funzioni definite come parte del computer di destinazione e del compilatore, in genere nel codice .NET nativo classico.</span><span class="sxs-lookup"><span data-stu-id="3d69d-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="3d69d-107">In generale, computer di destinazione diversi possono avere implementazioni del preludio diverse appropriate per ogni sistema.</span><span class="sxs-lookup"><span data-stu-id="3d69d-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="3d69d-108">**Canone**: operazioni e funzioni definite in Q# basate sulla logica definita nel preludio.</span><span class="sxs-lookup"><span data-stu-id="3d69d-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="3d69d-109">L'implementazione del canone è indipendente rispetto ai computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3d69d-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="3d69d-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="3d69d-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>