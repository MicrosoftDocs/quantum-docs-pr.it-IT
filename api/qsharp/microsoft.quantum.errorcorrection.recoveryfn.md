---
uid: Microsoft.Quantum.ErrorCorrection.RecoveryFn
title: Tipo definito dall'utente RecoveryFn
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoveryFn
qsharp.summary: Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.
ms.openlocfilehash: 6f4db7312fadbd8ca4c6b8533f78c2c5a886f30e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712197"
---
# <a name="recoveryfn-user-defined-type"></a><span data-ttu-id="dfa50-102">Tipo definito dall'utente RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="dfa50-102">RecoveryFn user defined type</span></span>

<span data-ttu-id="dfa50-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="dfa50-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="dfa50-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dfa50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dfa50-105">Tipo per la funzione che esegue il mapping di una sindrome di errore a una sequenza di `Pauli[]` operazioni che correggono l'errore rilevato.</span><span class="sxs-lookup"><span data-stu-id="dfa50-105">Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.</span></span>

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

