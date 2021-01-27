---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845237"
---
# <a name="xbits-function"></a><span data-ttu-id="2ca7b-102">XBits (funzione)</span><span class="sxs-lookup"><span data-stu-id="2ca7b-102">XBits function</span></span>

<span data-ttu-id="2ca7b-103">Spazio dei nomi: [Microsoft. Quantum. bit per bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="2ca7b-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="2ca7b-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2ca7b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2ca7b-105">Restituisce un Integer che rappresenta i bit X di una matrice di operatori Pauli.</span><span class="sxs-lookup"><span data-stu-id="2ca7b-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="2ca7b-106">Input</span><span class="sxs-lookup"><span data-stu-id="2ca7b-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="2ca7b-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="2ca7b-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="2ca7b-108">Matrice di operatori Pauli da rappresentare come Integer.</span><span class="sxs-lookup"><span data-stu-id="2ca7b-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="2ca7b-109">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2ca7b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2ca7b-110">Integer $x $ con rappresentazione binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, dove $p _i = $0 se `paulis[i]` è `PauliI` o `PauliZ` e dove $p _i = $1 se `paulis[i]` è `PauliX` o `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="2ca7b-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2ca7b-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="2ca7b-111">Remarks</span></span>

<span data-ttu-id="2ca7b-112">La funzione genererà un'eccezione se la lunghezza della `paulis` matrice è maggiore di 63.</span><span class="sxs-lookup"><span data-stu-id="2ca7b-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ca7b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ca7b-113">See Also</span></span>

- [<span data-ttu-id="2ca7b-114">Microsoft. Quantum. bit per bit. ZBits</span><span class="sxs-lookup"><span data-stu-id="2ca7b-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)