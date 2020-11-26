---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: Tipo definito dall'utente EncodeOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: 18d6df6037b1fe66a171acea1936fcb9ba1b27e5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200901"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="45563-102">Tipo definito dall'utente EncodeOp</span><span class="sxs-lookup"><span data-stu-id="45563-102">EncodeOp user defined type</span></span>

<span data-ttu-id="45563-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="45563-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="45563-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45563-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45563-105">Rappresenta un'operazione che consente di codificare un registro fisico in un registro logico, usando il qubits di Scratch fornito.</span><span class="sxs-lookup"><span data-stu-id="45563-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="45563-106">Il primo argomento viene considerato come il registro fisico che verrà codificato, mentre il secondo argomento viene considerato come il registro Scratch che verrà usato.</span><span class="sxs-lookup"><span data-stu-id="45563-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

