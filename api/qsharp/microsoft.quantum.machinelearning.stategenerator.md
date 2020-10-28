---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Tipo definito dall'utente StateGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722396"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="11d1e-102">Tipo definito dall'utente StateGenerator</span><span class="sxs-lookup"><span data-stu-id="11d1e-102">StateGenerator user defined type</span></span>

<span data-ttu-id="11d1e-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="11d1e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="11d1e-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="11d1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="11d1e-105">Descrive un'operazione che prepara un input specificato a un classificatore sequenziale.</span><span class="sxs-lookup"><span data-stu-id="11d1e-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="11d1e-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="11d1e-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="11d1e-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11d1e-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11d1e-108">Numero di qubits in cui è definito l'input codificato.</span><span class="sxs-lookup"><span data-stu-id="11d1e-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="11d1e-109">Preparazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) LittleEndian ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="11d1e-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="11d1e-110">Operazione che prepara l'input codificato in un registro Little-Endian di `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="11d1e-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>