---
uid: Microsoft.Quantum.Arrays.Flattened
title: Funzione Flat
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848625"
---
# <a name="flattened-function"></a><span data-ttu-id="02308-102">Funzione Flat</span><span class="sxs-lookup"><span data-stu-id="02308-102">Flattened function</span></span>

<span data-ttu-id="02308-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="02308-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="02308-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02308-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02308-105">Data una matrice di matrici, restituisce la concatenazione di tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="02308-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="02308-106">Input</span><span class="sxs-lookup"><span data-stu-id="02308-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="02308-107">matrici:' t [] []</span><span class="sxs-lookup"><span data-stu-id="02308-107">arrays : 'T[][]</span></span>

<span data-ttu-id="02308-108">Matrice di matrici.</span><span class="sxs-lookup"><span data-stu-id="02308-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="02308-109">Output:' t []</span><span class="sxs-lookup"><span data-stu-id="02308-109">Output : 'T[]</span></span>

<span data-ttu-id="02308-110">Concatenazione di tutte le matrici.</span><span class="sxs-lookup"><span data-stu-id="02308-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="02308-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="02308-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02308-112">T</span><span class="sxs-lookup"><span data-stu-id="02308-112">'T</span></span>

<span data-ttu-id="02308-113">Tipo di `array` elementi.</span><span class="sxs-lookup"><span data-stu-id="02308-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="02308-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="02308-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```