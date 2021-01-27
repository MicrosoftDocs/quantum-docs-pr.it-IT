---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: Tipo definito dall'utente MCMTMask
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855367"
---
# <a name="mcmtmask-user-defined-type"></a>Tipo definito dall'utente MCMTMask

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tipo per rappresentare un controllo Toffoli multiplo a più destinazioni.

Il primo Integer è una maschera di bit per le linee di controllo.  Gli indici di bit impostati corrispondono agli indici di riga di controllo.

Il secondo Integer è una maschera di bit per le linee di destinazione.  Gli indici di bit impostati corrispondono agli indici di riga di destinazione.

Gli indici di bit di entrambi i numeri interi devono essere non contigui.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Elementi denominati

### <a name="controlmask--int"></a>ControlMask: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask: [int](xref:microsoft.quantum.lang-ref.int)

