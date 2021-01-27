---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848355"
---
# <a name="realmod-function"></a><span data-ttu-id="6013e-102">RealMod (funzione)</span><span class="sxs-lookup"><span data-stu-id="6013e-102">RealMod function</span></span>

<span data-ttu-id="6013e-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6013e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6013e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6013e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6013e-105">Calcola il modulo tra due numeri reali.</span><span class="sxs-lookup"><span data-stu-id="6013e-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="6013e-106">Input</span><span class="sxs-lookup"><span data-stu-id="6013e-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="6013e-107">valore: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6013e-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6013e-108">Un numero reale $x $ per eseguire il modulo di.</span><span class="sxs-lookup"><span data-stu-id="6013e-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="6013e-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6013e-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6013e-110">Numero reale da usare per il modulo di $x $ rispetto a.</span><span class="sxs-lookup"><span data-stu-id="6013e-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="6013e-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6013e-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6013e-112">Valore minimo che deve essere restituito da questa funzione.</span><span class="sxs-lookup"><span data-stu-id="6013e-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="6013e-113">Output: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6013e-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="6013e-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6013e-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="6013e-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="6013e-115">Remarks</span></span>

<span data-ttu-id="6013e-116">Questa funzione calcola il modulo reale eseguendo il wrapping della riga reale sul cerchio di unità, quindi individuando l'angolo nel cerchio di unità corrispondente all'input.</span><span class="sxs-lookup"><span data-stu-id="6013e-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="6013e-117">L' `minValue` input specifica quindi la posizione in cui tagliare il cerchio di unità.</span><span class="sxs-lookup"><span data-stu-id="6013e-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>