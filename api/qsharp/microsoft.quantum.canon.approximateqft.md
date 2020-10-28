---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operazione ApproximateQFT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716775"
---
# <a name="approximateqft-operation"></a>Operazione ApproximateQFT

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Applicare la trasformazione AQFT (Quantum Fourier Transform) approssimativa a un registro Quantum.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Input

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

parametro di approssimazione che determina a quale livello vengono eliminate le rotazioni Z controllate che si verificano nel circuito QFT.

Il parametro di approssimazione a determina il livello di eliminazione delle rotazioni Z, ovvero un ∈ {0.. n} e tutte le rotazioni Z 2 π/2K, dove k>a vengono rimosse dal circuito QFT. È noto che per k >= log ₂ (n) + log ₂ (1/ε) + 3 One può associare | | QFT-AQFT | |<ε.


### <a name="qs--bigendian"></a>QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

registro Quantum di n qubits a cui viene applicata la trasformazione del quantum Quantum approssimativo.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

AQFT richiede i cancelli a rotazione Z nel formato 2 π/2K e Hadamard.

Si presuppone che l'input e l'output siano codificati nella codifica big endian.

## <a name="references"></a>Riferimenti

- [*M. Roetteler, th. Beth* , appl. algebra ENG. commune. Comput. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv: quanti-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)