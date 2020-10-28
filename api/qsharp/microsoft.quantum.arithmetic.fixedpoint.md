---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: Tipo definito dall'utente di FixedPoint
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721146"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="2063b-102">Tipo definito dall'utente di FixedPoint</span><span class="sxs-lookup"><span data-stu-id="2063b-102">FixedPoint user defined type</span></span>

<span data-ttu-id="2063b-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2063b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2063b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2063b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2063b-105">Rappresenta un registro di qubits che codifica un numero a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="2063b-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="2063b-106">È costituito da un numero intero uguale al numero di qubits a sinistra del punto binario, ad esempio, qubits di peso maggiore o uguale a 1 e un registro Quantum.</span><span class="sxs-lookup"><span data-stu-id="2063b-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

