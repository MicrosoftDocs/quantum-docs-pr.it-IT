---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operazione ApproximateQFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850317"
---
# <a name="approximateqft-operation"></a>Operazione ApproximateQFT

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applicare la trasformazione AQFT (Quantum Fourier Transform) approssimativa a un registro Quantum.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
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

- [*M. Roetteler, th. Beth*, appl. algebra ENG. commune. Comput. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv: quanti-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)