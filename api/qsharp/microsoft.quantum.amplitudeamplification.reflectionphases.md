---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definito dall'utente ReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191347"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="d4942-102">Tipo definito dall'utente ReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="d4942-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="d4942-103">Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d4942-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d4942-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4942-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4942-105">Fasi per una sequenza di riflessioni parziali nell'amplificazione dell'ampiezza.</span><span class="sxs-lookup"><span data-stu-id="d4942-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="d4942-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="d4942-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="d4942-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d4942-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d4942-108">Matrice di fasi per la reflection sullo stato di avvio.</span><span class="sxs-lookup"><span data-stu-id="d4942-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="d4942-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d4942-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d4942-110">Matrice di fasi per la reflection sullo stato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4942-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4942-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d4942-111">Remarks</span></span>

<span data-ttu-id="d4942-112">Entrambe le matrici devono essere di uguale lunghezza.</span><span class="sxs-lookup"><span data-stu-id="d4942-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="d4942-113">Si noti che in molti casi, la prima fase sullo stato di avvio e l'ultima fase sullo stato di destinazione introduce un cambio di fase globale e può essere impostato su $0 $.</span><span class="sxs-lookup"><span data-stu-id="d4942-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>