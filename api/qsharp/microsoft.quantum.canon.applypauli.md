---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Operazione ApplyPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844749"
---
# <a name="applypauli-operation"></a><span data-ttu-id="ba69f-102">Operazione ApplyPauli</span><span class="sxs-lookup"><span data-stu-id="ba69f-102">ApplyPauli operation</span></span>

<span data-ttu-id="ba69f-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ba69f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ba69f-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba69f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba69f-105">Dato un operatore Pauli multiqubit, applica l'operazione corrispondente a un registro.</span><span class="sxs-lookup"><span data-stu-id="ba69f-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ba69f-106">Input</span><span class="sxs-lookup"><span data-stu-id="ba69f-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="ba69f-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ba69f-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ba69f-108">Operatore Pauli multiqubit rappresentato come una matrice di operatori Pauli a qubit singolo.</span><span class="sxs-lookup"><span data-stu-id="ba69f-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ba69f-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ba69f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ba69f-110">Eseguire la registrazione per applicare l'operazione di Pauli specificata in.</span><span class="sxs-lookup"><span data-stu-id="ba69f-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ba69f-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ba69f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="ba69f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba69f-112">Example</span></span>

<span data-ttu-id="ba69f-113">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="ba69f-113">The following are equivalent:</span></span>

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

<span data-ttu-id="ba69f-114">e</span><span class="sxs-lookup"><span data-stu-id="ba69f-114">and</span></span>

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```