---
title: 'Librerie standard Q #-conversioni di tipi | Microsoft Docs'
description: 'Librerie standard Q #-conversioni di tipi'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184475"
---
# <a name="type-conversions"></a><span data-ttu-id="18288-103">Conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="18288-103">Type Conversions</span></span> #

<span data-ttu-id="18288-104">Q # è un linguaggio **fortemente tipizzato** .</span><span class="sxs-lookup"><span data-stu-id="18288-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="18288-105">In particolare, Q # non esegue il cast implicito tra tipi distinti.</span><span class="sxs-lookup"><span data-stu-id="18288-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="18288-106">Ad esempio, `1 + 2.0` non è un'espressione Q # valida.</span><span class="sxs-lookup"><span data-stu-id="18288-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="18288-107">Q # fornisce invece un'ampia gamma di funzioni di conversione dei tipi per la costruzione di nuovi valori di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="18288-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="18288-108">Ad esempio, <xref:microsoft.quantum.core.length> ha un tipo di output di `Int`, pertanto l'output deve essere convertito in un `Double` prima di poter essere usato come parte di un'espressione a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="18288-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="18288-109">Questa operazione può essere eseguita usando la funzione <xref:microsoft.quantum.convert.intasdouble>:</span><span class="sxs-lookup"><span data-stu-id="18288-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="18288-110">Lo spazio dei nomi <xref:microsoft.quantum.convert> fornisce funzioni comuni di conversione dei tipi per l'utilizzo dei tipi incorporati di base, ad esempio `Int`, `Double`, `BigInt`, `Result`e `Bool`:</span><span class="sxs-lookup"><span data-stu-id="18288-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="18288-111">Lo spazio dei nomi <xref:microsoft.quantum.convert> fornisce anche alcune conversioni più esotiche, ad esempio `FunctionAsOperation`, che converte le funzioni `'T -> 'U` in nuove operazioni `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="18288-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="18288-112">Infine, la libreria standard Q # fornisce una serie di tipi definiti dall'utente, ad esempio <xref:microsoft.quantum.math.complex> e <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="18288-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="18288-113">Insieme a questi tipi, la libreria standard fornisce funzioni come <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="18288-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
