---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: Tipo definito dall'utente JWOptimizedHTerms
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: e86e9da42ce002babdd4d161eca4646cca7071ab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224956"
---
# <a name="jwoptimizedhterms-user-defined-type"></a><span data-ttu-id="d81de-102">Tipo definito dall'utente JWOptimizedHTerms</span><span class="sxs-lookup"><span data-stu-id="d81de-102">JWOptimizedHTerms user defined type</span></span>

<span data-ttu-id="d81de-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d81de-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d81de-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d81de-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="d81de-105">Formato dei dati passati da C# a Q # per rappresentare i termini dell'hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="d81de-105">Format of data passed from C# to Q# to represent terms of the Hamiltonian.</span></span>
<span data-ttu-id="d81de-106">Il significato dei dati rappresentati è determinato dall'algoritmo che lo riceve.</span><span class="sxs-lookup"><span data-stu-id="d81de-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

