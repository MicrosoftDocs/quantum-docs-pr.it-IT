---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: Operazione ApplyUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859216"
---
# <a name="applyunitary-operation"></a>Operazione ApplyUnitary

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applica il controllo definito da 2 ^ n x 2 ^ n matrice unitaria.

Ha esito negativo se la matrice non è unitaria o ha dimensioni errate.

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="unitary--complex"></a>unitario: [complesso](xref:Microsoft.Quantum.Math.Complex)[] []

2 ^ n x 2 ^ n matrice unitaria che descrive l'operazione.
Se la matrice non è unitaria o non è di dimensioni appropriate, genera un'eccezione.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubits a cui applicare l'operazione-registro di lunghezza n.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

