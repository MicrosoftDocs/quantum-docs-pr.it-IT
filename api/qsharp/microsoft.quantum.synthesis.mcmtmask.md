---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definito dall'utente MCMTMask
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725501"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="ca61f-102">Tipo definito dall'utente MCMTMask</span><span class="sxs-lookup"><span data-stu-id="ca61f-102">MCMTMask user defined type</span></span>

<span data-ttu-id="ca61f-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ca61f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ca61f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca61f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca61f-105">Tipo per rappresentare un controllo Toffoli multiplo a più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="ca61f-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="ca61f-106">Il primo Integer è una maschera di bit per le linee di controllo.</span><span class="sxs-lookup"><span data-stu-id="ca61f-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="ca61f-107">Gli indici di bit impostati corrispondono agli indici di riga di controllo.</span><span class="sxs-lookup"><span data-stu-id="ca61f-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="ca61f-108">Il secondo Integer è una maschera di bit per le linee di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ca61f-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="ca61f-109">Gli indici di bit impostati corrispondono agli indici di riga di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ca61f-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="ca61f-110">Gli indici di bit di entrambi i numeri interi devono essere non contigui.</span><span class="sxs-lookup"><span data-stu-id="ca61f-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="ca61f-111">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="ca61f-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="ca61f-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ca61f-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="ca61f-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ca61f-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

