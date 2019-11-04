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
# <a name="type-conversions"></a>Conversioni di tipi #

Q # è un linguaggio **fortemente tipizzato** .
In particolare, Q # non esegue il cast implicito tra tipi distinti. Ad esempio, `1 + 2.0` non è un'espressione Q # valida.
Q # fornisce invece un'ampia gamma di funzioni di conversione dei tipi per la costruzione di nuovi valori di un determinato tipo.

Ad esempio, <xref:microsoft.quantum.core.length> ha un tipo di output di `Int`, pertanto l'output deve essere convertito in un `Double` prima di poter essere usato come parte di un'espressione a virgola mobile.
Questa operazione può essere eseguita usando la funzione <xref:microsoft.quantum.convert.intasdouble>:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

Lo spazio dei nomi <xref:microsoft.quantum.convert> fornisce funzioni comuni di conversione dei tipi per l'utilizzo dei tipi incorporati di base, ad esempio `Int`, `Double`, `BigInt`, `Result`e `Bool`:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

Lo spazio dei nomi <xref:microsoft.quantum.convert> fornisce anche alcune conversioni più esotiche, ad esempio `FunctionAsOperation`, che converte le funzioni `'T -> 'U` in nuove operazioni `'T => 'U`.

Infine, la libreria standard Q # fornisce una serie di tipi definiti dall'utente, ad esempio <xref:microsoft.quantum.math.complex> e <xref:microsoft.quantum.arithmetic.littleendian>.
Insieme a questi tipi, la libreria standard fornisce funzioni come <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
