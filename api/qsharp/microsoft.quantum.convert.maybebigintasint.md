---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: d0a598497e8a8f019bbd8da7db1c6cc4d7bde017
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224276"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="dd4b3-102">MaybeBigIntAsInt (funzione)</span><span class="sxs-lookup"><span data-stu-id="dd4b3-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="dd4b3-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="dd4b3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="dd4b3-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dd4b3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dd4b3-105">Converte un valore Big Integer specificato in un intero equivalente, se possibile.</span><span class="sxs-lookup"><span data-stu-id="dd4b3-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="dd4b3-106">La funzione restituisce una coppia dell'intero risultante e un flag booleano che è true, se e solo se è possibile la conversione.</span><span class="sxs-lookup"><span data-stu-id="dd4b3-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="dd4b3-107">Input</span><span class="sxs-lookup"><span data-stu-id="dd4b3-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="dd4b3-108">r: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dd4b3-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="dd4b3-109">Output: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))</span><span class="sxs-lookup"><span data-stu-id="dd4b3-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="dd4b3-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="dd4b3-110">Remarks</span></span>

<span data-ttu-id="dd4b3-111">Per ulteriori informazioni, vedere il [costruttore C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="dd4b3-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>