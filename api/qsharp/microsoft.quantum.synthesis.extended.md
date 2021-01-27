---
uid: Microsoft.Quantum.Synthesis.Extended
title: Funzione estesa
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855481"
---
# <a name="extended-function"></a><span data-ttu-id="5942f-102">Funzione estesa</span><span class="sxs-lookup"><span data-stu-id="5942f-102">Extended function</span></span>

<span data-ttu-id="5942f-103">Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5942f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5942f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5942f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5942f-105">Estende uno spettro con coefficienti invertiti</span><span class="sxs-lookup"><span data-stu-id="5942f-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="5942f-106">Input</span><span class="sxs-lookup"><span data-stu-id="5942f-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="5942f-107">Spectrum: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5942f-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5942f-108">Coefficienti spettrali</span><span class="sxs-lookup"><span data-stu-id="5942f-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="5942f-109">Output: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5942f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5942f-110">Coefficienti seguiti da copia invertita</span><span class="sxs-lookup"><span data-stu-id="5942f-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="5942f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="5942f-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```