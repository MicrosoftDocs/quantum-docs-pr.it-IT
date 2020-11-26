---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definito dall'utente di FixedPoint
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223103"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="a3d6e-102">Tipo definito dall'utente di FixedPoint</span><span class="sxs-lookup"><span data-stu-id="a3d6e-102">FixedPoint user defined type</span></span>

<span data-ttu-id="a3d6e-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a3d6e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a3d6e-104">Pacchetto: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a3d6e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a3d6e-105">Rappresenta un registro di qubits che codifica un numero a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="a3d6e-106">È costituito da un numero intero uguale al numero di qubits a sinistra del punto binario, ad esempio, qubits di peso maggiore o uguale a 1 e un registro Quantum.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

