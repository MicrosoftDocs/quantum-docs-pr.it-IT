---
title: 'Conversioni di tipi nelle librerie standard Q #'
description: "Informazioni sulle funzioni di conversione dei tipi comuni e definite dall'utente nelle librerie standard di Q #."
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275008"
---
# <a name="type-conversions"></a>Conversione di tipi #

Q # è un linguaggio **fortemente tipizzato** .
In particolare, Q # non esegue il cast implicito tra tipi distinti. Ad esempio, `1 + 2.0` non è un'espressione Q # valida.
Q # fornisce invece un'ampia gamma di funzioni di conversione dei tipi per la costruzione di nuovi valori di un determinato tipo.

Ad esempio, <xref:microsoft.quantum.core.length> ha un tipo di output di `Int` , pertanto l'output deve essere prima convertito in un oggetto `Double` prima di poter essere usato come parte di un'espressione a virgola mobile.
Questa operazione può essere eseguita usando la <xref:microsoft.quantum.convert.intasdouble> funzione:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

Lo <xref:microsoft.quantum.convert> spazio dei nomi fornisce funzioni comuni di conversione dei tipi per l'utilizzo dei tipi incorporati di base, ad esempio `Int` ,, `Double` `BigInt` , `Result` e `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

Lo <xref:microsoft.quantum.convert> spazio dei nomi fornisce anche alcune conversioni più esotiche, ad esempio `FunctionAsOperation` , che convertono `'T -> 'U` le funzioni in nuove operazioni `'T => 'U` .

Infine, la libreria standard Q # fornisce una serie di tipi definiti dall'utente, ad esempio <xref:microsoft.quantum.math.complex> e <xref:microsoft.quantum.arithmetic.littleendian> .
Insieme a questi tipi, la libreria standard fornisce funzioni come <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
