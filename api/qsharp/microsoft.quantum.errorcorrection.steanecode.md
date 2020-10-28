---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712183"
---
# <a name="steanecode-function"></a>SteaneCode (funzione)

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Restituisce un valore CSS che rappresenta il codificatore di codice Steane ⟦ 7, 1, 3 ⟧ e il decodificatore con misurazione della sindrome sul posto.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Output: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Oggetto di tipo CSS che raccoglie tutti i dati rilevanti per eseguire la codifica e la correzione degli errori per il codice Steane ⟧ ⟦ 7, 1, 3.

## <a name="remarks"></a>Commenti

Questo codice è stato trovato nel documento seguente:

- A. Steane, "interferenza di più particelle e correzione degli errori quantistici", proc. Roy. Soc. Lond. A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.