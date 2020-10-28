---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712046"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="0e49b-102">TableLookupRecovery (funzione)</span><span class="sxs-lookup"><span data-stu-id="0e49b-102">TableLookupRecovery function</span></span>

<span data-ttu-id="0e49b-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0e49b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0e49b-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e49b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e49b-105">Per una tabella specificata di operazioni di Pauli in un determinato registro di qubits, questa funzione restituisce un oggetto di tipo `RecoveryFn` che contiene tutte le informazioni necessarie per eseguire una decodifica della ricerca di tabella rispetto alla matrice di operazioni di Pauli specificata.</span><span class="sxs-lookup"><span data-stu-id="0e49b-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="0e49b-106">Input</span><span class="sxs-lookup"><span data-stu-id="0e49b-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="0e49b-107">tabella: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="0e49b-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="0e49b-108">Tabella delle operazioni di Pauli che operano su un determinato registro qubit</span><span class="sxs-lookup"><span data-stu-id="0e49b-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="0e49b-109">Output: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="0e49b-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="0e49b-110">Oggetto di tipo `RecoveryFn` , ad esempio una mappa `Syndrome -> Pauli[]` che associa a una matrice di sindromi specificata un'operazione di correzione di Pauli corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0e49b-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>