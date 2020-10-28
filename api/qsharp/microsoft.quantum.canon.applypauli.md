---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Operazione ApplyPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717814"
---
# <a name="applypauli-operation"></a><span data-ttu-id="48e63-102">Operazione ApplyPauli</span><span class="sxs-lookup"><span data-stu-id="48e63-102">ApplyPauli operation</span></span>

<span data-ttu-id="48e63-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="48e63-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="48e63-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48e63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48e63-105">Dato un operatore Pauli multiqubit, applica l'operazione corrispondente a un registro.</span><span class="sxs-lookup"><span data-stu-id="48e63-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="48e63-106">Input</span><span class="sxs-lookup"><span data-stu-id="48e63-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="48e63-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="48e63-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="48e63-108">Operatore Pauli multiqubit rappresentato come una matrice di operatori Pauli a qubit singolo.</span><span class="sxs-lookup"><span data-stu-id="48e63-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="48e63-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="48e63-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="48e63-110">Eseguire la registrazione per applicare l'operazione di Pauli specificata in.</span><span class="sxs-lookup"><span data-stu-id="48e63-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48e63-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48e63-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

