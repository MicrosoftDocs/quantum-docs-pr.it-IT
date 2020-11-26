---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204063"
---
# <a name="isnotzero-function"></a><span data-ttu-id="f5409-102">IsNotZero (funzione)</span><span class="sxs-lookup"><span data-stu-id="f5409-102">IsNotZero function</span></span>

<span data-ttu-id="f5409-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f5409-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="f5409-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f5409-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f5409-105">Verifica se un `Double` numero non è approssimativamente pari a zero.</span><span class="sxs-lookup"><span data-stu-id="f5409-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f5409-106">Input</span><span class="sxs-lookup"><span data-stu-id="f5409-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="f5409-107">numero: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f5409-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f5409-108">Numero da controllare</span><span class="sxs-lookup"><span data-stu-id="f5409-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="f5409-109">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f5409-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f5409-110">Restituisce true se il `number` valore assoluto di è maggiore di `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="f5409-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>