---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840896"
---
# <a name="composedoutput-function"></a><span data-ttu-id="60477-102">ComposedOutput (funzione)</span><span class="sxs-lookup"><span data-stu-id="60477-102">ComposedOutput function</span></span>

<span data-ttu-id="60477-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60477-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60477-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60477-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60477-105">Restituisce l'output della composizione di `inner` e `outer` per un input specificato.</span><span class="sxs-lookup"><span data-stu-id="60477-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="60477-106">Input</span><span class="sxs-lookup"><span data-stu-id="60477-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="60477-107">Outer:' U->' V</span><span class="sxs-lookup"><span data-stu-id="60477-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="60477-108">Inner: t->' U</span><span class="sxs-lookup"><span data-stu-id="60477-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="60477-109">destinazione:' t</span><span class="sxs-lookup"><span data-stu-id="60477-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="60477-110">Output:' V</span><span class="sxs-lookup"><span data-stu-id="60477-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="60477-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="60477-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60477-112">T</span><span class="sxs-lookup"><span data-stu-id="60477-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="60477-113">' U</span><span class="sxs-lookup"><span data-stu-id="60477-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="60477-114">' V</span><span class="sxs-lookup"><span data-stu-id="60477-114">'V</span></span>

