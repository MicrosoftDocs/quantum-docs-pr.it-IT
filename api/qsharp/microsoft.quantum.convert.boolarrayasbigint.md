---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713614"
---
# <a name="boolarrayasbigint-function"></a>BoolArrayAsBigInt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


Converte una matrice specificata di valori booleani in un intero grande equivalente.
L'elemento 0 della matrice è il bit meno significativo dell'Integer grande.

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a>Input

### <a name="a--bool"></a>a: [bool](xref:microsoft.quantum.lang-ref.bool)[]





## <a name="output--bigint"></a>Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Commenti

Per ulteriori informazioni, vedere il [costruttore C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .