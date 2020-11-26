---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definito dall'utente MCMTMask
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203019"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="dc555-102">Tipo definito dall'utente MCMTMask</span><span class="sxs-lookup"><span data-stu-id="dc555-102">MCMTMask user defined type</span></span>

<span data-ttu-id="dc555-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="dc555-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="dc555-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc555-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc555-105">Tipo per rappresentare un controllo Toffoli multiplo a più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="dc555-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="dc555-106">Il primo Integer è una maschera di bit per le linee di controllo.</span><span class="sxs-lookup"><span data-stu-id="dc555-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="dc555-107">Gli indici di bit impostati corrispondono agli indici di riga di controllo.</span><span class="sxs-lookup"><span data-stu-id="dc555-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="dc555-108">Il secondo Integer è una maschera di bit per le linee di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dc555-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="dc555-109">Gli indici di bit impostati corrispondono agli indici di riga di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dc555-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="dc555-110">Gli indici di bit di entrambi i numeri interi devono essere non contigui.</span><span class="sxs-lookup"><span data-stu-id="dc555-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="dc555-111">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="dc555-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="dc555-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc555-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="dc555-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc555-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

