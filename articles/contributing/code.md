---
title: Contributo del codice | Microsoft Docs
description: Contributi al codice
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: 3ff15a744bf15924564d5a8fee54f4fbce4c04ee
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864424"
---
# <a name="contributing-code"></a>Contributi di codice #

Oltre a segnalare i problemi e a migliorare la documentazione, il codice aggiunto al quantum Development Kit può essere un metodo molto diretto per aiutare i colleghi nella community di programmazione quantistica.
Contribuendo al codice, è possibile risolvere i problemi, fornire nuovi esempi, rendere le librerie esistenti più facili da usare o persino aggiungere funzionalità completamente nuove.

In questa guida verrà illustrato in dettaglio un po' di ciò che si cerca quando si esaminano le richieste pull per aiutare il contributo a eseguire le operazioni più valide.

## <a name="what-we-look-for"></a>Cosa si cerca ##

Un contributo di codice ideale si basa sul lavoro esistente in un repository di Quantum Development Kit per risolvere i problemi, espandere le funzionalità esistenti o aggiungere nuove funzionalità che rientrano nell'ambito di un repository.
Quando si accetta un contributo del codice, questo diventa parte del kit di sviluppo Quantum stesso, in modo che le nuove funzionalità vengano rilasciate, mantenute e sviluppate nello stesso modo in cui si trova il resto del kit di sviluppo Quantum.
Pertanto, è utile quando la funzionalità aggiunta da un contributo è ben collaudata e documentata.

### <a name="unit-tests"></a>Unit test ###

Le funzioni, le operazioni e i tipi definiti dall'utente di Q # che costituiscono librerie come il canone vengono testati automaticamente come parte dello sviluppo nel repository [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .
Quando viene aperta una nuova richiesta pull, ad esempio, la configurazione [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) verificherà che le modifiche nella richiesta pull non interrompano le funzionalità esistenti da cui dipende la community di programmazione quantistica.

Con la versione più recente di Q #, unit test vengono definiti usando l'attributo `@Test("QuantumSimulator")`. L'argomento può essere "QuantumSimulator", "ToffoliSimulator", "TraceSimulator" o qualsiasi nome completo che specifichi la destinazione di esecuzione. Diversi attributi che definiscono destinazioni di esecuzione diverse possono essere collegati allo stesso oggetto chiamabile. Alcuni dei test usano ancora il pacchetto [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) deprecato che espone tutte le funzioni e le operazioni Q # che terminano con `Test` al Framework [xUnit](https://xunit.github.io/) . Questo pacchetto non è più necessario per la definizione degli unit test. 

La funzione seguente viene usata per garantire che le funzioni <xref:microsoft.quantum.canon.fst> e <xref:microsoft.quantum.canon.snd> restituiscono entrambi gli output corretti in un esempio rappresentativo.
Se l'output di `Fst` o `Snd` non è corretto, viene utilizzata l'istruzione `fail` per impedire che il test abbia esito negativo.

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

È possibile controllare le condizioni più complesse usando le tecniche descritte nella [sezione test](xref:microsoft.quantum.libraries.diagnostics) della Guida alle librerie standard.
Ad esempio, il test seguente controlla che `H(q); X(q); H(q);` come chiamato da <xref:microsoft.quantum.canon.applywith> esegue la stessa operazione `Z(q)`.

```qsharp
@Test("QuantumSimulator")
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

Quando si aggiungono nuove funzionalità, è consigliabile aggiungere anche nuovi test per assicurarsi che il contributo funzioni come previsto.
In questo modo il resto della community può gestire e sviluppare la funzionalità e, in particolare, gli altri sviluppatori sanno che possono basarsi sulla propria funzionalità.

> [!NOTE]
> Questa operazione funziona anche in altro modo.
> Se è presente una funzionalità esistente in cui mancano alcuni test, l'aggiunta del code coverage dei test comporterebbe un notevole contributo alla community.

Localmente, gli unit test possono essere eseguiti con Esplora test di Visual Studio o con il comando `dotnet test`, in modo che sia possibile controllare il contributo prima di aprire una richiesta pull.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a>Quando si rifiuterà una richiesta pull ##

In alcuni casi, la richiesta pull verrà rifiutata per un contributo.
In tal caso, non significa che si tratta di un problema, in quanto esistono diversi motivi per cui potrebbe non essere possibile accettare un particolare contributo.
Probabilmente, più comunemente, un contributo alla community di programmazione quantistica è molto utile, ma i repository di Quantum Development Kit non sono il posto giusto per lo sviluppo.
In questi casi, è consigliabile fare in modo che il proprio repository---parte della potenza del kit di sviluppo di Quantum sia semplice creare e distribuire librerie personalizzate usando GitHub e NuGet.org, nello stesso modo in cui si distribuiscono la canonica e la chimica librerie attualmente disponibili.

In altri casi, è possibile rifiutare un contributo valido semplicemente perché non è ancora pronto per la manutenzione e lo sviluppo.
Può essere difficile eseguire tutte le operazioni, in modo da pianificare le funzionalità più adatte per lavorare come roadmap.
Questo può essere un altro caso in cui il rilascio di una funzionalità come libreria di terze parti può essere molto utile.
In alternativa, è possibile chiedere all'utente di modificare una funzionalità per adattarla al nostro piano di guida, in modo da poter eseguire le operazioni migliori.

Verranno anche richieste modifiche a una richiesta pull se è necessaria una maggiore documentazione o unit test per facilitarne l'uso o se lo stile è diverso dal resto delle librerie Q # che rende più difficile per gli utenti trovare la propria funzionalità.
In questi casi, si tenterà di offrire un suggerimento per le revisioni del codice sugli elementi che possono essere aggiunti o modificati per facilitare l'inclusione del contributo.

Infine, non è possibile accettare contributi che causino danni alla community di calcolo quantistica, come illustrato nel [codice di comportamento open source di Microsoft](https://opensource.microsoft.com/codeofconduct/).
Vogliamo assicurarci che i contributi soddisfino l'intera community di calcolo quantistica, sia nella sua attuale diversità, che in futuro man mano che cresce per diventare ancora più inclusivo.
Per realizzare questo obiettivo, siamo lieti di aiutarti.

## <a name="next-steps"></a>Passaggi successivi ##

Grazie per aver contribuito a rendere Quantum Development Kit un'ottima risorsa per l'intera community di programmazione quantistica.
Per altre informazioni, continuare con la guida seguente sullo stile Q #.

> [!div class="nextstepaction"]
> [Informazioni sulle linee guida di stile Q #](xref:microsoft.quantum.contributing.style)
