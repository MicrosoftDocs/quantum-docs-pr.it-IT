---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operazione DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853682"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="d75b2-102">Operazione DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="d75b2-102">DrawRandomBool operation</span></span>

<span data-ttu-id="d75b2-103">Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="d75b2-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="d75b2-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d75b2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d75b2-105">Data la probabilità di esito positivo, restituisce una singola versione di valutazione di Bernoulli che è true con la probabilità specificata.</span><span class="sxs-lookup"><span data-stu-id="d75b2-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="d75b2-106">Input</span><span class="sxs-lookup"><span data-stu-id="d75b2-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="d75b2-107">successProbability: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d75b2-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d75b2-108">Probabilità con la quale `true` deve essere restituito.</span><span class="sxs-lookup"><span data-stu-id="d75b2-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d75b2-109">Output: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d75b2-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d75b2-110">`true` con probabilità `successProbability` e `false` con probabilità `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="d75b2-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="d75b2-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d75b2-111">Example</span></span>

<span data-ttu-id="d75b2-112">Il seguente esempio di frammento di codice Q # esegue il capovolgimento da una moneta distorta:</span><span class="sxs-lookup"><span data-stu-id="d75b2-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```