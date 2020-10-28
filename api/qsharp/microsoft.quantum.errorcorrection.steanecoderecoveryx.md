---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712130"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX (funzione)

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Decodificatore per la parte X del gruppo stabilizzatore del codice Quantum Steane 7, 1, 3 ⟧ di ⟦.

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>Input

### <a name="syndrome--syndrome"></a>Syndrome: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Matrice di sindromi ottenuta dalla misurazione della parte X dello stabilizzatore.



## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Matrice di operazioni di Pauli che, quando applicato al sistema quantistico codificato, corregge l'errore corrispondente a `syndrome` .

## <a name="remarks"></a>Commenti

Il decodificatore scelto usa la proprietà del codice CSS del codice Steane ⟧ ⟦ 7, 1, 3, ovvero corregge gli errori X e Z separatamente. Una proprietà del codice è che la posizione della X, rispettivamente, della correzione Z da applicare è la codifica a 3 bit della sindrome X, rispettivamente, Z quando viene considerato un numero intero.

## <a name="references"></a>Riferimenti

- D. Gottesman, "codici stabilizzatori e correzione errori Quantum", Ph.D. tesi, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)