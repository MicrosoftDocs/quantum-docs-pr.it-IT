---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853064"
---
# <a name="steanecode-function"></a><span data-ttu-id="fbb62-102">SteaneCode (funzione)</span><span class="sxs-lookup"><span data-stu-id="fbb62-102">SteaneCode function</span></span>

<span data-ttu-id="fbb62-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="fbb62-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="fbb62-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbb62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbb62-105">Restituisce un valore CSS che rappresenta il codificatore di codice Steane ⟦ 7, 1, 3 ⟧ e il decodificatore con misurazione della sindrome sul posto.</span><span class="sxs-lookup"><span data-stu-id="fbb62-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="fbb62-106">Output: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="fbb62-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="fbb62-107">Oggetto di tipo CSS che raccoglie tutti i dati rilevanti per eseguire la codifica e la correzione degli errori per il codice Steane ⟧ ⟦ 7, 1, 3.</span><span class="sxs-lookup"><span data-stu-id="fbb62-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="fbb62-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="fbb62-108">Remarks</span></span>

<span data-ttu-id="fbb62-109">Questo codice è stato trovato nel documento seguente:</span><span class="sxs-lookup"><span data-stu-id="fbb62-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="fbb62-110">R.</span><span class="sxs-lookup"><span data-stu-id="fbb62-110">A.</span></span> <span data-ttu-id="fbb62-111">Steane, "interferenza di più particelle e correzione degli errori quantistici", proc.</span><span class="sxs-lookup"><span data-stu-id="fbb62-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="fbb62-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="fbb62-112">Roy.</span></span> <span data-ttu-id="fbb62-113">Soc. Lond.</span><span class="sxs-lookup"><span data-stu-id="fbb62-113">Soc. Lond.</span></span> <span data-ttu-id="fbb62-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="fbb62-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>