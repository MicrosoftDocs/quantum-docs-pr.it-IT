---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: Operazione ApplyCurriedOpCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: df534a3156ac3f5411161c6faf4d39759e49fbed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218904"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="ad384-102">Operazione ApplyCurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="ad384-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="ad384-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ad384-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ad384-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad384-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ad384-105">Input</span><span class="sxs-lookup"><span data-stu-id="ad384-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="ad384-106">curriedOp:' t->' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ad384-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="ad384-107">primo:' t</span><span class="sxs-lookup"><span data-stu-id="ad384-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="ad384-108">secondo:' U</span><span class="sxs-lookup"><span data-stu-id="ad384-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ad384-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad384-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ad384-110">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="ad384-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad384-111">T</span><span class="sxs-lookup"><span data-stu-id="ad384-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="ad384-112">' U</span><span class="sxs-lookup"><span data-stu-id="ad384-112">'U</span></span>

