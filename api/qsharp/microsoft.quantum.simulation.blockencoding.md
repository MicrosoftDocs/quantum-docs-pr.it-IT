---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Tipo definito dall'utente BlockEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 70cd18f04cbd449f4818ba3b40580303137f84db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857625"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="97ebe-102">Tipo definito dall'utente BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="97ebe-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="97ebe-103">Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="97ebe-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="97ebe-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97ebe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97ebe-105">Rappresenta un elemento unitario in cui un operatore arbitrario di interesse è codificato nel blocco superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="97ebe-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="97ebe-106">Ovvero, un `BlockEncoding` è un elemento unitario $U $ in cui un operatore arbitrario $H $ di interesse che agisce sul Registro di sistema `s` è codificato nel blocco superiore sinistro corrispondente allo stato ausiliario $ \ket {0} _A $.</span><span class="sxs-lookup"><span data-stu-id="97ebe-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="97ebe-107">Cioè</span><span class="sxs-lookup"><span data-stu-id="97ebe-107">That is,</span></span>

<span data-ttu-id="97ebe-108">$ $ \begin{align} (\bra {0} _A \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="97ebe-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

