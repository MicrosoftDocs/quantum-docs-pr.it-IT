---
title: Conversioni di tipi nelle Q# librerie standard
description: Informazioni sulle funzioni di conversione dei tipi comuni e definite dall'utente nelle Q# librerie standard.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691111"
---
# <a name="type-conversions"></a>Conversione di tipi #

Q# è un linguaggio **fortemente tipizzato** .
In particolare, non Q# esegue il cast implicito tra tipi distinti. Ad esempio, `1 + 2.0` non è un' Q# espressione valida.
Fornisce invece Q# diverse funzioni di conversione dei tipi per la costruzione di nuovi valori di un determinato tipo.

Ad esempio, <xref:Microsoft.Quantum.Core.Length> ha un tipo di output di `Int` , pertanto l'output deve essere prima convertito in un oggetto `Double` prima di poter essere usato come parte di un'espressione a virgola mobile.
Questa operazione può essere eseguita usando la <xref:Microsoft.Quantum.Convert.IntAsDouble> funzione:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

Lo <xref:Microsoft.Quantum.Convert> spazio dei nomi fornisce funzioni comuni di conversione dei tipi per l'utilizzo dei tipi incorporati di base, ad esempio `Int` ,, `Double` `BigInt` , `Result` e `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

Lo <xref:Microsoft.Quantum.Convert> spazio dei nomi fornisce anche alcune conversioni più esotiche, ad esempio `FunctionAsOperation` , che convertono `'T -> 'U` le funzioni in nuove operazioni `'T => 'U` .

Infine, la Q# libreria standard fornisce una serie di tipi definiti dall'utente, ad esempio <xref:Microsoft.Quantum.Math.Complex> e <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Insieme a questi tipi, la libreria standard fornisce funzioni come <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
