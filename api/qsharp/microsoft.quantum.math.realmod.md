---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720402"
---
# <a name="realmod-function"></a><span data-ttu-id="f6652-102">RealMod (funzione)</span><span class="sxs-lookup"><span data-stu-id="f6652-102">RealMod function</span></span>

<span data-ttu-id="f6652-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f6652-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f6652-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6652-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6652-105">Calcola il modulo tra due numeri reali.</span><span class="sxs-lookup"><span data-stu-id="f6652-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="f6652-106">Input</span><span class="sxs-lookup"><span data-stu-id="f6652-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="f6652-107">valore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6652-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6652-108">Un numero reale $x $ per eseguire il modulo di.</span><span class="sxs-lookup"><span data-stu-id="f6652-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="f6652-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6652-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6652-110">Numero reale da usare per il modulo di $x $ rispetto a.</span><span class="sxs-lookup"><span data-stu-id="f6652-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="f6652-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6652-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6652-112">Valore minimo che deve essere restituito da questa funzione.</span><span class="sxs-lookup"><span data-stu-id="f6652-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="f6652-113">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6652-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="f6652-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="f6652-114">Remarks</span></span>

<span data-ttu-id="f6652-115">Questa funzione calcola il modulo reale eseguendo il wrapping della riga reale sul cerchio di unità, quindi individuando l'angolo nel cerchio di unità corrispondente all'input.</span><span class="sxs-lookup"><span data-stu-id="f6652-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="f6652-116">L' `minValue` input specifica quindi la posizione in cui tagliare il cerchio di unità.</span><span class="sxs-lookup"><span data-stu-id="f6652-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>