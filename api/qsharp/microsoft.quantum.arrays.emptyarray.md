---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846167"
---
# <a name="emptyarray-function"></a><span data-ttu-id="25826-102">EmptyArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="25826-102">EmptyArray function</span></span>

<span data-ttu-id="25826-103">Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="25826-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="25826-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="25826-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="25826-105">Restituisce la matrice vuota di un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="25826-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="25826-106">Output:' TElement []</span><span class="sxs-lookup"><span data-stu-id="25826-106">Output : 'TElement[]</span></span>

<span data-ttu-id="25826-107">Matrice vuota.</span><span class="sxs-lookup"><span data-stu-id="25826-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="25826-108">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="25826-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="25826-109">' TElement</span><span class="sxs-lookup"><span data-stu-id="25826-109">'TElement</span></span>

<span data-ttu-id="25826-110">Tipo di elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="25826-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="25826-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="25826-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```