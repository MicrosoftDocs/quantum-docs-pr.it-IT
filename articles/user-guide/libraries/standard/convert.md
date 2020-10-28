---
title: 'Conversioni di tipi nelle :::no-loc(Q#)::: librerie standard'
description: "Informazioni sulle funzioni di conversione dei tipi comuni e definite dall'utente nelle :::no-loc(Q#)::: librerie standard."
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691111"
---
# <a name="type-conversions"></a><span data-ttu-id="ba202-103">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="ba202-103">Type Conversions</span></span> #

<span data-ttu-id="ba202-104">:::no-loc(Q#)::: è un linguaggio **fortemente tipizzato** .</span><span class="sxs-lookup"><span data-stu-id="ba202-104">:::no-loc(Q#)::: is a **strongly-typed** language.</span></span>
<span data-ttu-id="ba202-105">In particolare, non :::no-loc(Q#)::: esegue il cast implicito tra tipi distinti.</span><span class="sxs-lookup"><span data-stu-id="ba202-105">In particular, :::no-loc(Q#)::: does not implicitly cast between distinct types.</span></span> <span data-ttu-id="ba202-106">Ad esempio, `1 + 2.0` non è un' :::no-loc(Q#)::: espressione valida.</span><span class="sxs-lookup"><span data-stu-id="ba202-106">For instance, `1 + 2.0` is not a valid :::no-loc(Q#)::: expression.</span></span>
<span data-ttu-id="ba202-107">Fornisce invece :::no-loc(Q#)::: diverse funzioni di conversione dei tipi per la costruzione di nuovi valori di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="ba202-107">Rather, :::no-loc(Q#)::: provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="ba202-108">Ad esempio, <xref:Microsoft.Quantum.Core.Length> ha un tipo di output di `Int` , pertanto l'output deve essere prima convertito in un oggetto `Double` prima di poter essere usato come parte di un'espressione a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="ba202-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="ba202-109">Questa operazione può essere eseguita usando la <xref:Microsoft.Quantum.Convert.IntAsDouble> funzione:</span><span class="sxs-lookup"><span data-stu-id="ba202-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="ba202-110">Lo <xref:Microsoft.Quantum.Convert> spazio dei nomi fornisce funzioni comuni di conversione dei tipi per l'utilizzo dei tipi incorporati di base, ad esempio `Int` ,, `Double` `BigInt` , `Result` e `Bool` :</span><span class="sxs-lookup"><span data-stu-id="ba202-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="ba202-111">Lo <xref:Microsoft.Quantum.Convert> spazio dei nomi fornisce anche alcune conversioni più esotiche, ad esempio `FunctionAsOperation` , che convertono `'T -> 'U` le funzioni in nuove operazioni `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="ba202-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="ba202-112">Infine, la :::no-loc(Q#)::: libreria standard fornisce una serie di tipi definiti dall'utente, ad esempio <xref:Microsoft.Quantum.Math.Complex> e <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="ba202-112">Finally, the :::no-loc(Q#)::: standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="ba202-113">Insieme a questi tipi, la libreria standard fornisce funzioni come <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="ba202-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```:::no-loc(Q#):::
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
