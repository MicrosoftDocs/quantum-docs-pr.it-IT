---
uid: Microsoft.Quantum.Math.ComplexPolar
title: Tipo definito dall'utente ComplexPolar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 0c18c3f02cb036f22a68b6e4b46fd19049dc34cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709649"
---
# <a name="complexpolar-user-defined-type"></a><span data-ttu-id="96a8f-102">Tipo definito dall'utente ComplexPolar</span><span class="sxs-lookup"><span data-stu-id="96a8f-102">ComplexPolar user defined type</span></span>

<span data-ttu-id="96a8f-103">Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="96a8f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="96a8f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96a8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96a8f-105">Rappresenta un numero complesso in formato polare.</span><span class="sxs-lookup"><span data-stu-id="96a8f-105">Represents a complex number in polar form.</span></span>

<span data-ttu-id="96a8f-106">La rappresentazione polare di un numero complesso è $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="96a8f-106">The polar representation of a complex number is $c=r e^{i t}$.</span></span>

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a><span data-ttu-id="96a8f-107">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="96a8f-107">Named Items</span></span>

### <a name="magnitude--double"></a><span data-ttu-id="96a8f-108">Magnitude: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96a8f-108">Magnitude : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="96a8f-109">Il valore assoluto $r \ge $0 di $c $.</span><span class="sxs-lookup"><span data-stu-id="96a8f-109">The absolute value $r \ge 0$ of $c$.</span></span>
### <a name="argument--double"></a><span data-ttu-id="96a8f-110">Argomento: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="96a8f-110">Argument : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="96a8f-111">La fase $t \in \mathbb R $ di $c $.</span><span class="sxs-lookup"><span data-stu-id="96a8f-111">The phase $t \in \mathbb R$ of $c$.</span></span>