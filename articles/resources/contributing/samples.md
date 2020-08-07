---
title: Contributi agli esempi di Microsoft QDK
description: Informazioni su come aggiungere codice di esempio al Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 20da0e1765a242c172cc595f03d7791a0e8b8d2d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867512"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Contributi agli esempi per Quantum Development Kit

Se si è interessati a contribuire al codice nel [repository di esempi](https://github.com/Microsoft/Quantum), grazie per aver reso la community di sviluppo quantistica un posto migliore.

## <a name="the-quantum-development-kit-samples-repository"></a>Repository degli esempi di Quantum Development Kit

Per facilitare la preparazione del contributo per facilitare il più possibile, è utile esaminare rapidamente la disposizione del repository di esempi:

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

Ovvero, gli esempi nel [repository Microsoft/Quantum](https://github.com/microsoft/Quantum) vengono suddivisi in base all'area di interesse in cartelle diverse, ad esempio `algorithms/` , `arithmetic/` o `characterization/` .
All'interno della cartella per ogni area di interesse, ogni esempio è costituito da una singola cartella che raccoglie tutti gli elementi necessari a un utente per esplorare e utilizzare l'esempio.

## <a name="how-samples-are-structured"></a>Struttura degli esempi

Esaminando i file che compongono ogni cartella, è consigliabile approfondire l' [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) esempio.

| File              | Descrizione                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q#progetto utilizzato per compilare l'esempio con la .NET Core SDK |
| `Game.qs`         | Q#operazioni e funzioni per l'esempio                 |
| `Host.cs`         | Programma host C# usato per eseguire l'esempio                     |
| `host.py`         | Programma host Python usato per eseguire l'esempio                 |
| `README.md`       | Documentazione su cosa fa l'esempio e su come usarlo    |

Non tutti gli esempi avranno esattamente lo stesso set di file (ad esempio, alcuni esempi possono essere solo C#, altri potrebbero non avere un host Python o alcuni esempi potrebbero richiedere l'uso di file di dati auxillary).

## <a name="anatomy-of-a-helpful-readme-file"></a>Anatomia di un file Leggimi utile

Un file particolarmente importante, tuttavia, è il `README.md` file, in quanto gli utenti devono iniziare a usare l'esempio.

Ognuno `README.md` deve iniziare con alcuni metadati che consentono a docs.Microsoft.com/samples di trovare il contributo.

> [!div class="nextstepaction"]
> [Vedere come viene eseguito il rendering dell'esempio chsh-Game](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Questi metadati vengono forniti come [intestazione YAML](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) che indica le lingue analizzate dall'esempio (in genere, questo sarà `qsharp` , `csharp` e `python` ) e i prodotti trattati dall'esempio (in genere, solo `qdk` ).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample`Per visualizzare l'esempio in docs.Microsoft.com/samples, è necessario specificare la chiave nell'intestazione.
> Analogamente, `product` le `language` chiavi e sono fondamentali per aiutare gli utenti a trovare ed eseguire l'esempio.

Successivamente, è utile fornire una breve introduzione che indichi il risultato del nuovo esempio:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Gli utenti dell'esempio apprezzeranno anche la conoscenza di ciò che è necessario per eseguirlo (ad esempio, gli utenti hanno bisogno solo del quantum Development Kit o di software aggiuntivo, ad esempio node.js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

In questo modo, è possibile indicare agli utenti come eseguire l'esempio:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Infine, è utile indicare agli utenti la funzione di ogni file nell'esempio e dove possono andare per ulteriori informazioni:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Assicurarsi di usare gli URL assoluti qui, poiché l'esempio verrà visualizzato in un altro URL quando viene eseguito il rendering in docs.microsoft.com/samples.
