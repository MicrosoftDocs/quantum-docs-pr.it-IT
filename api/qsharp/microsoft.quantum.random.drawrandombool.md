---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operazione DrawRandomBool
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720279"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="ef130-102">Operazione DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="ef130-102">DrawRandomBool operation</span></span>

<span data-ttu-id="ef130-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ef130-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ef130-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef130-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef130-105">Data la probabilità di esito positivo, restituisce una singola versione di valutazione di Bernoulli che è true con la probabilità specificata.</span><span class="sxs-lookup"><span data-stu-id="ef130-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="ef130-106">Input</span><span class="sxs-lookup"><span data-stu-id="ef130-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="ef130-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ef130-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ef130-108">Probabilità con la quale `true` deve essere restituito.</span><span class="sxs-lookup"><span data-stu-id="ef130-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ef130-109">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ef130-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ef130-110">`true` con probabilità `successProbability` e `false` con probabilità `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="ef130-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>