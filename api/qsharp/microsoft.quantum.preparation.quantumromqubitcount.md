---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210404"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="685a4-102">QuantumROMQubitCount (funzione)</span><span class="sxs-lookup"><span data-stu-id="685a4-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="685a4-103">Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="685a4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="685a4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="685a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="685a4-105">QuantumROMQubitCount è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="685a4-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="685a4-106">Usare invece <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements>.</span><span class="sxs-lookup"><span data-stu-id="685a4-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="685a4-107">Restituisce il numero totale di qubits che devono essere allocati all'operazione restituita da `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="685a4-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="685a4-108">Input</span><span class="sxs-lookup"><span data-stu-id="685a4-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="685a4-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="685a4-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="685a4-110">Errore di destinazione $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="685a4-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="685a4-111">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="685a4-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="685a4-112">Numero di coefficienti specificati in `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="685a4-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="685a4-113">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="685a4-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="685a4-114">Primo parametro</span><span class="sxs-lookup"><span data-stu-id="685a4-114">First parameter</span></span>

<span data-ttu-id="685a4-115">Tupla `(x,(y,z))` `x = y + z` in cui è il numero totale di qubits allocato, `y` è il numero di qubits per il `LittleEndian` registro e `z` è il numero di Garbage qubits.</span><span class="sxs-lookup"><span data-stu-id="685a4-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>