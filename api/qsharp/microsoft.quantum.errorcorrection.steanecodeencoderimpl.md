---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Operazione SteaneCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712186"
---
# <a name="steanecodeencoderimpl-operation"></a>Operazione SteaneCodeEncoderImpl

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Operazione privata usata per implementare il codificatore di codice Steane e il decodificatore.

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="data--qubit"></a>dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

matrice contenente 1 qubit che rappresenta il qubit di input.


### <a name="scratch--qubit"></a>Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

matrice contenente 6 qubits che aggiungono ridondanza.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

