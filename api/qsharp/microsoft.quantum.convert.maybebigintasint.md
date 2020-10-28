---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713432"
---
# <a name="maybebigintasint-function"></a>MaybeBigIntAsInt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


Converte un valore Big Integer specificato in un intero equivalente, se possibile.
La funzione restituisce una coppia dell'intero risultante e un flag booleano che è true, se e solo se è possibile la conversione.

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a>Input

### <a name="a--bigint"></a>r: [bigint](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--intbool"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))



## <a name="remarks"></a>Commenti

Per ulteriori informazioni, vedere il [costruttore C# BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .