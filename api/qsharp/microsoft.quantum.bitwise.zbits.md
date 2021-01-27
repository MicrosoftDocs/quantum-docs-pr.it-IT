---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842070"
---
# <a name="zbits-function"></a><span data-ttu-id="8f7ec-102">ZBits (funzione)</span><span class="sxs-lookup"><span data-stu-id="8f7ec-102">ZBits function</span></span>

<span data-ttu-id="8f7ec-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="8f7ec-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="8f7ec-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8f7ec-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8f7ec-105">Restituisce un Integer che rappresenta i bit Z di una matrice di operatori Pauli.</span><span class="sxs-lookup"><span data-stu-id="8f7ec-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="8f7ec-106">Input</span><span class="sxs-lookup"><span data-stu-id="8f7ec-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="8f7ec-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="8f7ec-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="8f7ec-108">Matrice di operatori Pauli da rappresentare come Integer.</span><span class="sxs-lookup"><span data-stu-id="8f7ec-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="8f7ec-109">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8f7ec-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8f7ec-110">Integer $x $ con rappresentazione binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, dove $p _i = $0 se `paulis[i]` è `PauliI` o `PauliX` e dove $p _i = $1 se `paulis[i]` è `PauliY` o `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="8f7ec-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f7ec-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="8f7ec-111">Remarks</span></span>

<span data-ttu-id="8f7ec-112">La funzione genererà un'eccezione se la lunghezza della `paulis` matrice è maggiore di 63.</span><span class="sxs-lookup"><span data-stu-id="8f7ec-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f7ec-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f7ec-113">See Also</span></span>

- [<span data-ttu-id="8f7ec-114">Microsoft. Quantum. bit per bit. XBits</span><span class="sxs-lookup"><span data-stu-id="8f7ec-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)