---
uid: Microsoft.Quantum.Math.PlusA
title: Funzione PLUSa
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709607"
---
# <a name="plusa-function"></a><span data-ttu-id="5dec0-102">Funzione PLUSa</span><span class="sxs-lookup"><span data-stu-id="5dec0-102">PlusA function</span></span>

<span data-ttu-id="5dec0-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5dec0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5dec0-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5dec0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5dec0-105">Restituisce la somma (concatenazione) di due input.</span><span class="sxs-lookup"><span data-stu-id="5dec0-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="5dec0-106">Input</span><span class="sxs-lookup"><span data-stu-id="5dec0-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="5dec0-107">a:' elemento []</span><span class="sxs-lookup"><span data-stu-id="5dec0-107">a : 'Element[]</span></span>

<span data-ttu-id="5dec0-108">Primo input $a $ da sommare.</span><span class="sxs-lookup"><span data-stu-id="5dec0-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="5dec0-109">b:' elemento []</span><span class="sxs-lookup"><span data-stu-id="5dec0-109">b : 'Element[]</span></span>

<span data-ttu-id="5dec0-110">Secondo input $b $ da sommare.</span><span class="sxs-lookup"><span data-stu-id="5dec0-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="5dec0-111">Output:' elemento []</span><span class="sxs-lookup"><span data-stu-id="5dec0-111">Output : 'Element[]</span></span>

<span data-ttu-id="5dec0-112">La somma $a + b $.</span><span class="sxs-lookup"><span data-stu-id="5dec0-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5dec0-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5dec0-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="5dec0-114">' Elemento</span><span class="sxs-lookup"><span data-stu-id="5dec0-114">'Element</span></span>

<span data-ttu-id="5dec0-115">Tipo di ogni elemento in ognuna delle due matrici di input.</span><span class="sxs-lookup"><span data-stu-id="5dec0-115">The type of each element in each of the two input arrays.</span></span>