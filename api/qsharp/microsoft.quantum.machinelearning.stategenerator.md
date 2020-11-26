---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Tipo definito dall'utente StateGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211560"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="03915-102">Tipo definito dall'utente StateGenerator</span><span class="sxs-lookup"><span data-stu-id="03915-102">StateGenerator user defined type</span></span>

<span data-ttu-id="03915-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="03915-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="03915-104">Pacchetto: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="03915-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="03915-105">Descrive un'operazione che prepara un input specificato a un classificatore sequenziale.</span><span class="sxs-lookup"><span data-stu-id="03915-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="03915-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="03915-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="03915-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03915-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03915-108">Numero di qubits in cui è definito l'input codificato.</span><span class="sxs-lookup"><span data-stu-id="03915-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="03915-109">Preparazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) l' => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian è ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="03915-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="03915-110">Operazione che prepara l'input codificato in un registro Little-Endian di `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="03915-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>