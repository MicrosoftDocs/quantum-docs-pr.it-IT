---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Operazione CompareGTSI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721278"
---
# <a name="comparegtsi-operation"></a>Operazione CompareGTSI

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Wrapper per il confronto di interi con segno: `result = xs > ys` .

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="xs--signedlittleendian"></a>XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Primo $n numero di $ bit


### <a name="ys--signedlittleendian"></a>Ys: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Secondo numero $n $ bit


### <a name="result--qubit"></a>risultato: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Verrà capovolto se $xs > YS $



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

