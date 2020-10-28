---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709750"
---
# <a name="inputencoder-function"></a><span data-ttu-id="0a37d-102">InputEncoder (funzione)</span><span class="sxs-lookup"><span data-stu-id="0a37d-102">InputEncoder function</span></span>

<span data-ttu-id="0a37d-103">Spazio dei nomi: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0a37d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0a37d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a37d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a37d-105">Dato un set di coefficienti e una tolleranza, restituisce un'operazione di preparazione dello stato che prepara ogni coefficiente come l'ampiezza corrispondente di uno stato di base computazionale.</span><span class="sxs-lookup"><span data-stu-id="0a37d-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="0a37d-106">Input</span><span class="sxs-lookup"><span data-stu-id="0a37d-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="0a37d-107">coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0a37d-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0a37d-108">Coefficienti da codificare in uno stato di input.</span><span class="sxs-lookup"><span data-stu-id="0a37d-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="0a37d-109">Output: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="0a37d-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="0a37d-110">Operazione di preparazione dello stato che prepara i coefficienti specificati come stato di input in un determinato registro.</span><span class="sxs-lookup"><span data-stu-id="0a37d-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>