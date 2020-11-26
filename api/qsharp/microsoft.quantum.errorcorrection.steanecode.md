---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200476"
---
# <a name="steanecode-function"></a>SteaneCode (funzione)

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un valore CSS che rappresenta il codificatore di codice Steane ⟦ 7, 1, 3 ⟧ e il decodificatore con misurazione della sindrome sul posto.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Output: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Oggetto di tipo CSS che raccoglie tutti i dati rilevanti per eseguire la codifica e la correzione degli errori per il codice Steane ⟧ ⟦ 7, 1, 3.

## <a name="remarks"></a>Commenti

Questo codice è stato trovato nel documento seguente:

- R. Steane, "interferenza di più particelle e correzione degli errori quantistici", proc. Roy. Soc. Lond. A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.