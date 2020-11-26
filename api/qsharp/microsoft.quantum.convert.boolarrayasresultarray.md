---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224463"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="22f57-102">BoolArrayAsResultArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="22f57-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="22f57-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="22f57-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="22f57-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22f57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22f57-105">Converte un `Bool[]` tipo in un `Result[]` tipo, dove `true` viene mappato a `One` e `false` viene mappato a `Zero` .</span><span class="sxs-lookup"><span data-stu-id="22f57-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="22f57-106">Input</span><span class="sxs-lookup"><span data-stu-id="22f57-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="22f57-107">input: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="22f57-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="22f57-108">`Bool[]` da convertire.</span><span class="sxs-lookup"><span data-stu-id="22f57-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="22f57-109">Output: __non <Result> valido__[]</span><span class="sxs-lookup"><span data-stu-id="22f57-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="22f57-110">Oggetto `Result[]` che rappresenta l'istanza di `input`.</span><span class="sxs-lookup"><span data-stu-id="22f57-110">A `Result[]` representing the `input`.</span></span>