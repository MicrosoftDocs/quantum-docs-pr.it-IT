---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operazione DrawRandomBool
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192962"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="b3706-102">Operazione DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="b3706-102">DrawRandomBool operation</span></span>

<span data-ttu-id="b3706-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b3706-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b3706-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b3706-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b3706-105">Data la probabilità di esito positivo, restituisce una singola versione di valutazione di Bernoulli che è true con la probabilità specificata.</span><span class="sxs-lookup"><span data-stu-id="b3706-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b3706-106">Input</span><span class="sxs-lookup"><span data-stu-id="b3706-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="b3706-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b3706-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b3706-108">Probabilità con la quale `true` deve essere restituito.</span><span class="sxs-lookup"><span data-stu-id="b3706-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b3706-109">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b3706-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b3706-110">`true` con probabilità `successProbability` e `false` con probabilità `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="b3706-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>