---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: Operazione ApplyCurriedOpA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 100d8a42d6475d3cdda349a2e685a6fbfff23cdc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845082"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="18b78-102">Operazione ApplyCurriedOpA</span><span class="sxs-lookup"><span data-stu-id="18b78-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="18b78-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="18b78-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="18b78-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18b78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="18b78-105">Input</span><span class="sxs-lookup"><span data-stu-id="18b78-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="18b78-106">curriedOp:' t->' U => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="18b78-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="18b78-107">primo:' t</span><span class="sxs-lookup"><span data-stu-id="18b78-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="18b78-108">secondo:' U</span><span class="sxs-lookup"><span data-stu-id="18b78-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="18b78-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18b78-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="18b78-110">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="18b78-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="18b78-111">T</span><span class="sxs-lookup"><span data-stu-id="18b78-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="18b78-112">' U</span><span class="sxs-lookup"><span data-stu-id="18b78-112">'U</span></span>

