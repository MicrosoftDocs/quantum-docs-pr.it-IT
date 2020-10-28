---
uid: Microsoft.Quantum.ErrorCorrection.CSS
title: Tipo definito dall'utente CSS
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: CSS
qsharp.summary: Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.
ms.openlocfilehash: c5227c771ec2c7c81d05a28681745af641eebeaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712491"
---
# <a name="css-user-defined-type"></a>Tipo definito dall'utente CSS

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un codice Cantarelli – Shor – Steane (CSS) come definito dal codificatore, dal decodificatore e dalle procedure di misurazione della sindrome per gli `X` `Z` errori e, rispettivamente.

```qsharp

newtype CSS = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

