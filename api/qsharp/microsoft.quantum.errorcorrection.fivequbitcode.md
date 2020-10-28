---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712340"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode (funzione)

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Restituisce un valore QECC che rappresenta il codificatore di codice ⟧ ⟦ 5, 1, 3 e il decodificatore con misurazione della sindrome sul posto.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Output: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Restituisce un'implementazione di un codice di correzione degli errori Quantum specificando un `QECC` tipo.

## <a name="remarks"></a>Commenti

Questo codice è stato trovato in modo indipendente nei due documenti seguenti:

- C. H. Bennett, D. divincenzo, J. A. Smolin e W. K. Wootters, "misto di stato misto e correzione errori Quantum", "Inv. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 e
- R. Landini, C. Miquel, J. P. Paz e W. H. Zurek, "codice di correzione errore Quantum perfetto", "fisico. Rev. lett. 77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019