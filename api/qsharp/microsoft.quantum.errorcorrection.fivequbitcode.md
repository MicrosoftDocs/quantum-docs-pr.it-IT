---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712340"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="be3b8-102">FiveQubitCode (funzione)</span><span class="sxs-lookup"><span data-stu-id="be3b8-102">FiveQubitCode function</span></span>

<span data-ttu-id="be3b8-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="be3b8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="be3b8-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be3b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be3b8-105">Restituisce un valore QECC che rappresenta il codificatore di codice ⟧ ⟦ 5, 1, 3 e il decodificatore con misurazione della sindrome sul posto.</span><span class="sxs-lookup"><span data-stu-id="be3b8-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="be3b8-106">Output: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="be3b8-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="be3b8-107">Restituisce un'implementazione di un codice di correzione degli errori Quantum specificando un `QECC` tipo.</span><span class="sxs-lookup"><span data-stu-id="be3b8-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="be3b8-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="be3b8-108">Remarks</span></span>

<span data-ttu-id="be3b8-109">Questo codice è stato trovato in modo indipendente nei due documenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="be3b8-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="be3b8-110">C.</span><span class="sxs-lookup"><span data-stu-id="be3b8-110">C.</span></span> <span data-ttu-id="be3b8-111">H.</span><span class="sxs-lookup"><span data-stu-id="be3b8-111">H.</span></span> <span data-ttu-id="be3b8-112">Bennett, D. divincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="be3b8-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="be3b8-113">Smolin e W. K.</span><span class="sxs-lookup"><span data-stu-id="be3b8-113">Smolin and W. K.</span></span> <span data-ttu-id="be3b8-114">Wootters, "misto di stato misto e correzione errori Quantum", "Inv. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 e</span><span class="sxs-lookup"><span data-stu-id="be3b8-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="be3b8-115">R.</span><span class="sxs-lookup"><span data-stu-id="be3b8-115">R.</span></span> <span data-ttu-id="be3b8-116">Landini, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="be3b8-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="be3b8-117">Paz e W. H.</span><span class="sxs-lookup"><span data-stu-id="be3b8-117">Paz and W. H.</span></span> <span data-ttu-id="be3b8-118">Zurek, "codice di correzione errore Quantum perfetto", "fisico. Rev. lett.</span><span class="sxs-lookup"><span data-stu-id="be3b8-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="be3b8-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="be3b8-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>