---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operazione FiveQubitCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712337"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>Operazione FiveQubitCodeEncoderImpl

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Operazione privata usata per implementare il codificatore e il decodificatore qubit 5.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="data--qubit"></a>dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

matrice contenente 1 qubit che rappresenta il qubit di input.


### <a name="scratch--qubit"></a>Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

matrice contenente 4 qubits che aggiungono ridondanza.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Il codificatore particolare scelto è stato tratto dal documento V. Kliuchnikov e D. Maslov, "Optimization of Clifford Circuits," fisico. Rev. inv. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) e richiede un totale di 11 Gate.