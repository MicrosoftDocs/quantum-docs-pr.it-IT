---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228254"
---
# <a name="realmod-function"></a><span data-ttu-id="00dee-102">RealMod (funzione)</span><span class="sxs-lookup"><span data-stu-id="00dee-102">RealMod function</span></span>

<span data-ttu-id="00dee-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="00dee-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="00dee-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00dee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00dee-105">Calcola il modulo tra due numeri reali.</span><span class="sxs-lookup"><span data-stu-id="00dee-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="00dee-106">Input</span><span class="sxs-lookup"><span data-stu-id="00dee-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="00dee-107">valore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00dee-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00dee-108">Un numero reale $x $ per eseguire il modulo di.</span><span class="sxs-lookup"><span data-stu-id="00dee-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="00dee-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00dee-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00dee-110">Numero reale da usare per il modulo di $x $ rispetto a.</span><span class="sxs-lookup"><span data-stu-id="00dee-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="00dee-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00dee-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="00dee-112">Valore minimo che deve essere restituito da questa funzione.</span><span class="sxs-lookup"><span data-stu-id="00dee-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="00dee-113">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="00dee-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="00dee-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="00dee-114">Remarks</span></span>

<span data-ttu-id="00dee-115">Questa funzione calcola il modulo reale eseguendo il wrapping della riga reale sul cerchio di unità, quindi individuando l'angolo nel cerchio di unità corrispondente all'input.</span><span class="sxs-lookup"><span data-stu-id="00dee-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="00dee-116">L' `minValue` input specifica quindi la posizione in cui tagliare il cerchio di unità.</span><span class="sxs-lookup"><span data-stu-id="00dee-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>