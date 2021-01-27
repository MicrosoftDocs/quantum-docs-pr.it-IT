---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846235"
---
# <a name="constantarray-function"></a><span data-ttu-id="d9a72-102">ConstantArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="d9a72-102">ConstantArray function</span></span>

<span data-ttu-id="d9a72-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d9a72-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d9a72-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9a72-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9a72-105">Crea una matrice di lunghezza specificata con tutti gli elementi uguali al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="d9a72-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d9a72-106">Input</span><span class="sxs-lookup"><span data-stu-id="d9a72-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="d9a72-107">Lunghezza: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d9a72-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d9a72-108">Lunghezza della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="d9a72-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="d9a72-109">valore:' t</span><span class="sxs-lookup"><span data-stu-id="d9a72-109">value : 'T</span></span>

<span data-ttu-id="d9a72-110">Valore di ogni elemento della nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="d9a72-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="d9a72-111">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="d9a72-111">Output : 'T[]</span></span>

<span data-ttu-id="d9a72-112">Una nuova matrice di lunghezza `length` , in modo che ogni elemento sia `value` .</span><span class="sxs-lookup"><span data-stu-id="d9a72-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d9a72-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="d9a72-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9a72-114">T</span><span class="sxs-lookup"><span data-stu-id="d9a72-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="d9a72-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9a72-115">Example</span></span>

<span data-ttu-id="d9a72-116">Il codice seguente crea una matrice di 3 valori booleani, ognuno dei quali è uguale a `true` :</span><span class="sxs-lookup"><span data-stu-id="d9a72-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```