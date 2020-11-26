---
uid: Microsoft.Quantum.Math.PlusA
title: Funzione PLUSa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194832"
---
# <a name="plusa-function"></a><span data-ttu-id="427ca-102">Funzione PLUSa</span><span class="sxs-lookup"><span data-stu-id="427ca-102">PlusA function</span></span>

<span data-ttu-id="427ca-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="427ca-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="427ca-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="427ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="427ca-105">Restituisce la somma (concatenazione) di due input.</span><span class="sxs-lookup"><span data-stu-id="427ca-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="427ca-106">Input</span><span class="sxs-lookup"><span data-stu-id="427ca-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="427ca-107">a:' elemento []</span><span class="sxs-lookup"><span data-stu-id="427ca-107">a : 'Element[]</span></span>

<span data-ttu-id="427ca-108">Primo input $a $ da sommare.</span><span class="sxs-lookup"><span data-stu-id="427ca-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="427ca-109">b:' elemento []</span><span class="sxs-lookup"><span data-stu-id="427ca-109">b : 'Element[]</span></span>

<span data-ttu-id="427ca-110">Secondo input $b $ da sommare.</span><span class="sxs-lookup"><span data-stu-id="427ca-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="427ca-111">Output:' elemento []</span><span class="sxs-lookup"><span data-stu-id="427ca-111">Output : 'Element[]</span></span>

<span data-ttu-id="427ca-112">La somma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="427ca-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="427ca-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="427ca-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="427ca-114">' Elemento</span><span class="sxs-lookup"><span data-stu-id="427ca-114">'Element</span></span>

<span data-ttu-id="427ca-115">Tipo di ogni elemento in ognuna delle due matrici di input.</span><span class="sxs-lookup"><span data-stu-id="427ca-115">The type of each element in each of the two input arrays.</span></span>