---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Operazione AddI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721686"
---
# <a name="addi-operation"></a><span data-ttu-id="fa54b-102">Operazione AddI</span><span class="sxs-lookup"><span data-stu-id="fa54b-102">AddI operation</span></span>

<span data-ttu-id="fa54b-103">Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fa54b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fa54b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fa54b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fa54b-105">Sceglie automaticamente tra l'aggiunta con Carry e senza, a seconda delle dimensioni del registro `ys` .</span><span class="sxs-lookup"><span data-stu-id="fa54b-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="fa54b-106">Input</span><span class="sxs-lookup"><span data-stu-id="fa54b-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="fa54b-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fa54b-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fa54b-108">$n $ bit Addend.</span><span class="sxs-lookup"><span data-stu-id="fa54b-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="fa54b-109">Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fa54b-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fa54b-110">ADDEND con almeno $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="fa54b-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="fa54b-111">Manterrà il risultato.</span><span class="sxs-lookup"><span data-stu-id="fa54b-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa54b-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa54b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

