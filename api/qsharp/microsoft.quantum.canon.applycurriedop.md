---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: Operazione ApplyCurriedOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: ab652159fa64a95401d07998ed4aaae5c4dbb92e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219023"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="5015b-102">Operazione ApplyCurriedOp</span><span class="sxs-lookup"><span data-stu-id="5015b-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="5015b-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5015b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5015b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5015b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="5015b-105">Input</span><span class="sxs-lookup"><span data-stu-id="5015b-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="5015b-106">curriedOp: t->' U => [unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5015b-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="5015b-107">primo:' t</span><span class="sxs-lookup"><span data-stu-id="5015b-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="5015b-108">secondo:' U</span><span class="sxs-lookup"><span data-stu-id="5015b-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="5015b-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5015b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5015b-110">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5015b-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5015b-111">T</span><span class="sxs-lookup"><span data-stu-id="5015b-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="5015b-112">' U</span><span class="sxs-lookup"><span data-stu-id="5015b-112">'U</span></span>

