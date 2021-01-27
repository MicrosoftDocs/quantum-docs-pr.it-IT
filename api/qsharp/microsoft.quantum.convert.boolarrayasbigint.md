---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 220a733b94fd62cef21ab13e1cb3d3f973861506
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834404"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="b8b92-102">BoolArrayAsBigInt (funzione)</span><span class="sxs-lookup"><span data-stu-id="b8b92-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="b8b92-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="b8b92-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="b8b92-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b8b92-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b8b92-105">Converte una matrice specificata di valori booleani in un intero grande equivalente.</span><span class="sxs-lookup"><span data-stu-id="b8b92-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="b8b92-106">L'elemento 0 della matrice è il bit meno significativo dell'Integer grande.</span><span class="sxs-lookup"><span data-stu-id="b8b92-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="b8b92-107">Input</span><span class="sxs-lookup"><span data-stu-id="b8b92-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="b8b92-108">a: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b8b92-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="b8b92-109">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b8b92-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="b8b92-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="b8b92-110">Remarks</span></span>

<span data-ttu-id="b8b92-111">Per ulteriori informazioni, vedere il [costruttore C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="b8b92-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>