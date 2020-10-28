---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725473"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable (funzione)

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto [](https://nuget.org/packages/)


Regola la tabella di verità da una matrice di valori booleani in base al numero di variabili

Viene restituita una nuova matrice di lunghezza `2^numVars` , che può richiedere l'estensione delle `table` dimensioni con le `false` voci o il troncamento degli `2^numVars` elementi.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Input

### <a name="table--bool"></a>tabella: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabella di verità come matrice di valori di verità


### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)

Numero di variabili



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Ridimensionamento della tabella di verità