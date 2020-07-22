---
title: 'Algoritmi Quantum in Q #'
description: Informazioni sugli algoritmi di calcolo Quantum di base, tra cui l'amplificazione dell'ampiezza, la trasformazione di Fourier, i Adder e la stima della fase.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 7f4916353c53d6459356243098281ccb16b17278
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871315"
---
# <a name="quantum-algorithms"></a>Algoritmi Quantum #

## <a name="amplitude-amplification"></a>Amplificazione dell'altitudine ##

L' *amplificazione dell'ampiezza* è uno degli strumenti fondamentali del quantum computing. Si tratta dell'idea fondamentale che sottende la ricerca di Grover, la stima dell'ampiezza e molti algoritmi di Machine Learning Quantum.  Sono disponibili molte varianti e in Q # viene fornita una versione generale basata sull'amplificazione dell'ampiezza ignara con riflessi parziali per consentire l'area dell'applicazione più ampia.

L'idea centrale dietro l'amplificazione dell'ampiezza consiste nell'ampliare la probabilità di un risultato desiderato, eseguendo una sequenza di riflessi.  Queste riflessioni ruotano lo stato iniziale verso uno stato di destinazione desiderato, spesso definito stato contrassegnato.  In particolare, se la probabilità di misurare lo stato iniziale in uno stato contrassegnato è $ \sin ^ 2 (\theta) $, dopo aver applicato l'amplificazione dell'ampiezza $m $ volte la probabilità di successo diventa $ \sin ^ 2 ((2m + 1) \theta) $.  Ciò significa che se $ \theta = \ PI/[2 (2n + 1)] $ per un valore pari a $n $ then, l'amplificazione dell'ampiezza è in grado di aumentare la probabilità di successo fino al $100 \\ % $ dopo $n le iterazioni $ dell'amplificazione dell'ampiezza.  Dal momento che $ \theta = \sin ^ {-1} (\sqrt{\Pr (Success)}) $ questo significa che il numero di iterazioni necessarie per ottenere una riuscita in modo deterministico è quadratico inferiore al numero previsto necessario per trovare uno stato contrassegnato in modo non deterministico usando il campionamento casuale.

Ogni iterazione dell'amplificazione dell'ampiezza richiede la specifica di due operatori di Reflection. In particolare, se $Q $ è l'amplificazione dell'ampiezza iterata e $P _0 $ è un operatore proiettore sul sottospazio iniziale e $P _1 $ è il proiettore sul sottospazio contrassegnato, $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Tenere presente che un proiettore è un operatore Hermitiane con autovalori $ + $1 e $0 $ e, di conseguenza, $ (\boldone-2P_0) $ è unitario perché contiene autonomi che sono radici di Unity (in questo caso $ \pm $1). Si consideri ad esempio il caso della ricerca di Grover con lo stato iniziale $H ^ {\otimes n} \ket {0} $ e lo stato contrassegnato $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket {0} \bra {0} H ^ {\otimes n} $ e $P _1 = \ket{m}\bra{m} $.  Nella maggior parte delle applicazioni di amplificazione dell'ampiezza $P _0 $ sarà un proiettore con uno stato iniziale che significa che $P _0 = \boldone-2 \ KET {\ psi} \ Bra {\ psi} $ per some Vector $ \ket{\psi} $; Tuttavia, per l'ampiezza ignara amplication $P _0 $ generalmente proiettano su molti stati Quantum, ovvero la molteplicità dei autovalore $ + $1 di $P _0 $ è maggiore di $1 $.

La logica alla base dell'amplificazione dell'ampiezza segue direttamente dalla decomposizione autovettori di $Q $.  In particolare, il autovettori di $Q $ che lo stato iniziale ha un supporto diverso da zero può essere indicato come combinazioni lineari del autovettori $ + $1 di $P _0 $ e $P _1 $.  In particolare, lo stato iniziale per l'amplificazione dell'ampiezza (presupponendo che si tratta di un autovettore $ + $1 di $P _0 $) può essere scritto come $ $ \ket{\psi} = \frac{-i}{\sqrt {2} } \left (e ^ {i\theta} \ KET {\ psi_ +} + e ^ {-i\theta} \ KET {\ psi_-} \right), $ $ where $ \ket{\ psi_ \pm} $ sono autovettori di $Q $ con autovalori $e ^ {\pm 2i \ theta} $ e dispongono solo del supporto per la autovettori $ + $1 di $P _0 $ e $P _1 $.  Il fatto che gli autovalori siano $e ^ {\pm i \theta} $ implica che l'operatore $Q $ esegue una rotazione in un sottospazio bidimensionale specificato dai due proiettori e lo stato iniziale in cui l'angolo di rotazione è $2 \ Theta $.  Questo è il motivo per cui dopo la $m $ iterazioni di $Q $ la probabilità di successo è $ \sin ^ 2 ([2m + 1] \theta) $.

Un'altra proprietà utile che deriva da questo è che autovalore $ \theta $ è direttamente correlato alla probabilità che lo stato iniziale venga contrassegnato (nel caso in cui $P _0 $ sia un proiettore solo nello stato iniziale).  Poiché il valore di eigenphases di $Q $ è $2 \ Theta = 2 \ sin ^ {-1} (\sqrt{\Pr (Success)}), $ it segue che, se applichiamo la stima della fase a $Q $, possiamo apprendere la probabilità di successo per una procedura quantistica unitaria.  Questa operazione è utile perché richiede un minor numero di applicazioni della procedura quantistica per apprendere la probabilità di successo che altrimenti sarebbe necessario.

Q # introduce l'amplificazione dell'ampiezza come specializzazione dell'amplificazione dell'ampiezza ignara.  L'amplificazione dell'ampiezza ignara ottiene questo moniker perché il proiettore sul eigenspace iniziale non deve essere un proiettore sullo stato iniziale.  In questo senso, il protocollo è ignaro dello stato iniziale.  L'applicazione principale dell'amplificazione dell'ampiezza ignara è *costituita da alcune combinazioni lineari di metodi di simulazione hamiltoniana unitaria* , in cui lo stato iniziale è sconosciuto, ma diventa un registro ancilla nel protocollo di simulazione.  Se il registro ancilla deve essere misurato come valore fisso, ad esempio $0 $, questi metodi di simulazione applicano la trasformazione unitaria desiderata al qubits rimanente (denominato Registro di sistema).  Tutti gli altri risultati di misurazione portano tuttavia a un errore.  L'amplificazione dell'ampiezza indesiderata consente di incrementare la probabilità di successo di questa misurazione al $100 \\ % $ usando i motivi precedenti.  Inoltre, l'amplificazione dell'ampiezza ordinaria corrisponde al caso in cui il registro di sistema è vuoto.  Questo è il motivo per cui Q # usa l'amplificazione dell'ampiezza ignara come subroutine di amplificazione dell'ampiezza.

La routine generale ( `AmpAmpObliviousByReflectionPhases` ) ha due registri chiamati `ancillaRegister` e `systemRegister` . Accetta inoltre due Oracle per le riflessioni necessarie. `ReflectionOracle`Agisce solo su `ancillaRegister` mentre `ObliviousOracle` agisce congiuntamente su entrambi i registri. L'input per `ancillaRegister` deve essere inizializzato su un autostato-1 del primo operatore di Reflection $ \boldone-2P_1 $.

In genere, Oracle prepara lo stato in base al calcolo $ \ket{0...0} $. Nell'implementazione di `ancillaRegister` è costituito da un qubit ( `flagQubit` ) che controlla `stateOracle` e il resto del ancillas desiderato. `stateOracle`Viene applicato quando `flagQubit` è $ \ket {1} $.

Uno può anche fornire Oracle `StateOracle` e `ObliviousOracle` invece di riflessioni tramite una chiamata a `AmpAmpObliviousByOraclePhases` .

Come indicato in precedenza, l'amplificazione dell'ampiezza tradizionale è solo un caso speciale di queste routine in cui `ObliviousOracle` è l'operatore di identità e non sono presenti qubits di sistema (ovvero, `systemRegister` è vuoto). Se si desidera ottenere fasi per riflessioni parziali, ad esempio per la ricerca Grover, la funzione `AmpAmpPhasesStandard` è disponibile. `DatabaseSearch.qs`Per un'implementazione di esempio dell'algoritmo di Grover, fare riferimento a.

Si mettono in relazione le fasi di rotazione con singolo qubit alle fasi dell'operatore di reflection, come descritto nel documento di [G.H. Low, i. L. Chuang](https://arxiv.org/abs/1707.05391). Le fasi a virgola fissa utilizzate sono descritte in dettaglio in [Yoder, low e Chuang](https://arxiv.org/abs/1409.3305) insieme alle fasi in [low, Yoder e Chuang](https://arxiv.org/abs/1603.03996).

Per informazioni di base, è possibile iniziare dall' [amplificazione dell'ampiezza standard](https://arxiv.org/abs/quant-ph/0005055) , quindi passare a un'introduzione all' [amplificazione dell'ampiezza ignara](https://arxiv.org/abs/1312.1414) e infine alle generalizzazioni presentate in [low e Chuang](https://arxiv.org/abs/1610.06546). Una panoramica di questa intera area (in relazione alla simulazione Hamiltoniana) è stata fornita da [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf).

## <a name="quantum-fourier-transform"></a>Trasformazione Quantum Fourier ##

La trasformazione Fourier è uno strumento fondamentale di analisi classica ed è altrettanto importante per i calcoli quantistici.
Inoltre, l'efficienza della *trasformazione Quantum Fourier Transform* (QFT) supera di molto ciò che è possibile in un computer classico, rendendolo uno dei primi strumenti da scegliere quando si progetta un algoritmo Quantum.

Come generalizzazione approssimativa del QFT, viene fornita l' <xref:microsoft.quantum.canon.approximateqft> operazione che consente di ottimizzare ulteriormente le rotazioni che non sono strettamente necessarie per l'accuratezza algoritmica desiderata.
Il QFT approssimativo richiede l'operazione di diadico $Z $-Rotation <xref:microsoft.quantum.intrinsic.rfrac> e l' <xref:microsoft.quantum.intrinsic.h> operazione.
Si presuppone che l'input e l'output siano codificati nella codifica big endian---, ovvero qubit con index `0` è codificato nel bit più a sinistra (più alto) della rappresentazione di valori integer binari.
Questa operazione è allineata alla [notazione KET](xref:microsoft.quantum.concepts.dirac), perché un registro di tre qubits nello stato $ \ket {100} $ corrisponde a $q _0 $ si trova nello stato $ \ket {1} $ mentre $q _1 $ e $q _2 $ sono entrambi nello stato $ \ket {0} $.
Il parametro di approssimazione $a $ determina il livello di eliminazione delle $Z $-rotations, ad esempio $a \In [0.. n] $.
In questo caso tutti i $Z $-rotations $2 \ PI/2 ^ k $ dove $k > $ vengono rimossi dal circuito QFT.
Si noti che per $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3. uno può associare $ \\ | \operatorname{QFT}-\operatorname{AQFT} \\ | < \epsilon $.
Qui $ \\ | \cdot \\ | $ è la norma dell'operatore, che in questo caso è la radice quadrata della [autovalore](xref:microsoft.quantum.concepts.matrix-advanced) più grande di $ (\operatorname{QFT}-\operatorname{AQFT}) (\operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Aritmetico ##

Proprio come l'aritmetica svolge un ruolo centrale nell'elaborazione classica, è anche indispensabile in quantum computing.  Gli algoritmi come l'algoritmo di factoring di Shor, i metodi di simulazione quantistica e molti algoritmi oracolare si basano su operazioni aritmetiche coerenti.  La maggior parte degli approcci alla compilazione aritmetica sui circuiti Quantum Adder.  Il Adder più semplice accetta un input classico $b $ e aggiunge il valore a uno stato quantum contenente un Integer $ \ket{a} $.  In matematica, il Adder (che indica $ \operatorname{Add} (b) $ per l'input classico $b $) ha la proprietà che

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Questo circuito di base di Adder è più di un incremento rispetto a un Adder.
Può essere convertito in un Adder con due input Quantum tramite $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b}, $ $ usando $n applicazioni $ controllate di viperes nel formato \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda \_ {a \_ 0} \Left (\operatorname{Add} (1) \Right) \Lambda \_ {a \_ 1} \left (\operatorname{Add} (2) \right) \Lambda \_ {a \_ 2} \left (\operatorname{Add} (4) \right) \cdots \Lambda \_ {a \_ {n-1}} \left (\operatorname{Add} ({{n-1}}) \right) \ket{a}\ket{b} \\ \\ & = \ket{a} \ket{b + a}, \end{align} per $n interi a $ bit $a $ e $b $ e modulo di aggiunta $2 ^ n $.  Tenere presente che la notazione $ \Lambda \_ x (a) $ fa riferimento, per qualsiasi operazione $A $, alla versione controllata di tale operazione con il qubit $x $ As.

Analogamente, la moltiplicazione controllata in modo classico (un formato modulare di cui è essenziale per l'algoritmo di factoring di Shor) può essere eseguita usando una serie simile di aggiunte controllate: \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda \_ {x \_ 0} \Left (\operatorname{Add} (2 ^ 0 a) \Right) \Lambda \_ {a \_ 1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda \_ {a \_ 2} \left (\operatorname{Add} (2 ^ 2 a) \right) \cdots \Lambda \_ {x \_ {n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\ \\ & = \ket{x}\ket{b + AX}.
\end{align} esiste una sottigliezza con la moltiplicazione per i computer Quantum che è possibile notare dalla definizione di $ \operatorname{Mult} $ precedente.  A differenza dell'aggiunta, la versione Quantum di questo circuito archivia il prodotto degli input in un registro ausiliario anziché nel registro di input.  In questo esempio, il registro viene inizializzato con il valore $b $, ma in genere inizierà a contenere il valore zero.  Questa operazione è necessaria in perché in generale non è presente un inverso di moltiplicazione per il generale $a $ e $x $.  Poiché tutte le operazioni Quantum, Save Measurement, sono reversibili è necessario conservare informazioni sufficienti per invertire la moltiplicazione.  Per questo motivo il risultato viene archiviato in una matrice separata.  Questo espediente che consente di salvare l'output di un'operazione irreversibile, come la moltiplicazione, in un registro separato è noto come "Bennett Trick" dopo Charlie Bennett ed è uno strumento fondamentale per l'elaborazione reversibile e Quantum.

Molti circuiti Quantum sono stati proposti per l'aggiunta e ognuno Esplora un compromesso diverso in termini di numero di qubits (spazio) e numero di operazioni di controllo (tempo) necessarie.  In questo esempio vengono esaminati due vipere efficienti a livello di spazio inferiore, noti come Adder Draper e la vipera Beauregard.

### <a name="draper-adder"></a>Vipera Draper ###

Il Adder Draper è probabilmente uno dei Viper di quantum più eleganti, perché richiama direttamente le proprietà Quantum per eseguire l'addizione.  La conoscenza dietro la vipera Draper è che la trasformazione di Fourier può essere usata per tradurre i turni di fase in uno spostamento di bit.  Segue quindi questa operazione applicando una trasformazione di Fourier, applicando turni di fase appropriati e quindi anmutando la trasformazione di Fourier è possibile implementare un Adder.  A differenza di molti altri Viper che sono stati proposti, il Adder Draper USA in modo esplicito gli effetti quantistici introdotti tramite la trasformazione Quantum Fourier.  Non ha una controparte classica naturale.  Di seguito sono riportati i passaggi specifici del Adder Draper.

Si supponga di disporre di $n due registri qubit a $ bit che archiviano i numeri interi $a $ e $b $, per tutti $a $ $ $ \operatorname{QFT}\ket{a} = \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j}.
$ $ Se si definisce $ $ \ket{\Phi \_ k (a)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi a/2 ^ k} \ket {1} \right), $ $ quindi dopo alcune algebra si noterà che $ $ \operatorname{QFT}\ket{a} = \ket{\Phi \_ 1 (a)} \otimes \cdots \otimes \ket{\Phi \_ n (a)}.
$ $ Il percorso per l'esecuzione di un Adder diventa chiaro dopo aver osservato che la somma degli input può essere scritta come $ $ \ket{a + b} = \operatorname{QFT} ^ {-1} \ket{\Phi \_ 1 (a + b)} \otimes \cdots \otimes \ket{\Phi \_ n (a + b)}.
$ $ I numeri interi $b $ e $a $ possono quindi essere aggiunti eseguendo la rotazione controllata in fase di ogni qubits nella scomposizione usando i bit di $b $ come controlli.

Questa espansione può essere ulteriormente semplificata notando che per qualsiasi numero intero $j $ e un numero reale $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Il motivo è che se si ruota $360 ^ {\circ} $ degrees ($ 2 \ pi $ radianti) in un cerchio, si finisce esattamente nel punto in cui è stato avviato.  L'unica parte importante di $x $ per $e ^ {i2\pi x} $ è quindi la parte frazionaria di $x $.  In particolare, se si dispone di un'espansione binaria nel formato $x = y +0. x \_ 0x \_ 2 \ ldots x \_ n $ Then $e ^ {i2\pi x} = e ^ {i2\pi (0. x \_ 0x \_ 2 \ ldots x \_ {n-1})} $ e quindi $ $ \ket{\Phi \_ k (a + b)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi [a/2 ^ k +0. b \_ K\ldots b \_ 1]} \ket {1} \right). $ $ questo significa che se si esegue l'addizione incrementando ognuno dei fattori di tensore nell'espansione della trasformazione di Fourier di $ \ket{a} $, il numero di rotazioni viene compattato come $k $ diminuisce.  In questo modo si riduce notevolmente il numero di controlli Quantum necessari nel Viper.  Si denota la trasformazione di Fourier, l'addizione della fase e i passaggi di trasformazione di Fourier inversa che comprendono il Adder Draper come $ \operatorname{QFT} ^ {-1} \left (\Phi \\ \! \operatorname{Add}\right) \operatorname{QFT} $. Di seguito è riportato un circuito quantico che usa questa semplificazione per implementare l'intero processo.

![Vipera Draper mostrata come diagramma circuito](~/media/draper.svg)

Ogni controllo $e ^ {I2 \ PI/k} $ Gate nel circuito fa riferimento a un gate di fase controllata.  Tali cancelli hanno la proprietà che nella coppia di qubits su cui agiscono, $ \ket {00} \mapsto \ket {00} $ ma $ \ket {11} \mapsto e ^ {I2 \ PI/k} \ KET {11} $.  Questo circuito consente di eseguire l'addizione senza qubits aggiuntivi, oltre a quelli necessari per archiviare gli input e gli output.

### <a name="beauregard-adder"></a>Vipera Beauregard ###

Il Adder di Beauregard è un Adder modulare Quantum che usa il Viper di Draper per eseguire il modulo di aggiunta $N $ per un valore integer positivo di valore arbitrario $N $.  Il significato dei Viper modulari Quantum, ad esempio la vipera Beauregard, deriva in gran parte dal loro utilizzo nel passaggio modulare di elevamento a potenza nell'algoritmo di Shor per il factoring.  Un Adder modulare Quantum presenta l'azione seguente per l'input Quantum $ \ket{b} $ e l'input classico $a $ in cui $a $ e $b $ sono stati promessi come numeri interi mod $N $, vale a dire che sono nell'intervallo $ [0, \ldots, N-1] $.

$ $ \ket{b}\rightarrow \ket{b + a \Text{mod} N} = \begin{cases} \ket{b + a}, & b + a < N \\ \\ \ket{b + a-N}, & (b + a) \ge n \end{Cases}.
$$

Il Adder di Beauregard usa il Adder Draper o più specificamente $ \Phi \\ \! \operatorname{Add} $, per aggiungere $a $ e $b $ in fase.  USA quindi la stessa operazione per determinare se $a + b <N $ sottraendo $N $ e testando se $a + b-N<$0.  Il circuito archivia queste informazioni in un qubit ausiliario e quindi aggiunge $N $ Back The Register se $a + b<N $.  Termina quindi con l'annullamento del calcolo di questo bit ausiliario (questo passaggio è necessario per garantire che il ancilla possa essere deallocato dopo la chiamata al Adder).  Di seguito è riportato il circuito per la vipera Beauregard.

![Vipera Beauregard mostrata come diagramma circuito](~/media/beau.svg)

Il Gate $ \Phi \\ \! \operatorname{Add} $ ha lo stesso formato di $ \Phi \\ \! \operatorname{Add} $, ad eccezione del fatto che in questo contesto l'input è classico anziché Quantum.  In questo modo, le fasi controllate in $ \Phi \\ \! \operatorname{Add} $ possono essere sostituite con Gate di fase che possono essere compilate insieme in un minor numero di operazioni per ridurre sia il numero di qubits che il numero di porte necessarie per il Viper.

Per altri dettagli, vedere [M. Roetteler, th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) e [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Stima delle fasi del calcolo quantistico ###

Un'applicazione particolarmente importante della trasformazione Quantum Fourier consiste nell'apprendere gli autovalori degli operatori unitari, un problema noto come *valutazione della fase*.
Si consideri un $U unitario $ e uno stato $ \ket{\Phi} $ tale che $ \ket{\Phi} $ è un autostato di $U $ con Unknown autovalore $ \Phi $, \begin{Equation} U\ket {\ Phi} = \phi\ket{\Phi}.
\end{Equation} se si ha accesso solo a $U $ come Oracle, è possibile apprendere la fase $ \Phi $ usando il fatto che $Z $ rotazioni applicate alla destinazione di un'operazione controllata si propagano di nuovo nel controllo.

Si supponga che $V $ sia un'applicazione controllata di $U $, in modo che \begin{align} V (\ket {0} \otimes \ket{\Phi}) & = \ket \otimes \ket{\Phi} \textrm{ {0} \\ \\ e} V (\ket \otimes \ket{\Phi} {1} ) & = e ^ {i \Phi} {1} \ket \otimes \ket{\Phi}.
\end{align} then, by Linearity, \begin{align} V (\ket{+} \otimes \ket{\Phi}) & = \frac{(\ket {0} \otimes \ket{\Phi}) + e ^ {i \phi} (\ket {1} \otimes \ket{\Phi})} {\sqrt {2} }.
\end{align} è possibile raccogliere i termini per trovare che \begin{align} V (\ket{+} \otimes \ket{\Phi}) & = \frac{\ket {0} + e ^ {i \Phi} \ket {1} } {\sqrt {2} } \otimes \ket{\Phi} \\ \\ & = (R_1 (\Phi) \ket{+}) \otimes \ket{\Phi}, \end{align} dove $R _1 $ è l'unitario applicato dall' <xref:microsoft.quantum.intrinsic.r1> operazione.
Diversamente, l'effetto dell'applicazione di $V $ è esattamente uguale a quello applicato $R _1 $ con un angolo sconosciuto, anche se è possibile accedere solo $V $ come Oracle.
Quindi, nella parte restante di questa discussione verrà discussa la stima della fase in termini di $R _1 (\Phi) $, implementata usando il cosiddetto *contraccolpo della fase*.

Poiché il registro di controllo e di destinazione rimangono invariati dopo questo processo, è possibile riutilizzare $ \ket{\Phi} $ come destinazione di un'applicazione controllata di $U ^ $2 per preparare un secondo controllo qubit nello stato $R _1 (2 \Phi) \ket{+} $.
Continuando in questo modo, è possibile ottenere un registro nel formato \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \Phi) \ket{+} \\ \\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket {0} + \exp (i 2 ^ {j} \Phi) \ket {1} \right) \\ \\ & \propto \ Sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align} dove $n $ è il numero di bit di precisione necessari, e dove abbiamo usato $ {} \propto {} $ per indicare che è stato eliminato il fattore di normalizzazione di $1/\sqrt{2 ^ n} $.

Se si presuppone che $ \Phi = 2 \Pi p/2 ^ k $ per un numero intero $p $, questo viene riconosciuto come $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, dove $p _J $ è il $j ^ {\textrm{TH}} $ bit di $2 \Pi \Phi $.
Se si applica l'oggetto contiguo della trasformazione Quantum Fourier, viene pertanto ottenuta la rappresentazione binaria della fase codificata come stato quantum.

In Q # questo viene implementato dall' <xref:microsoft.quantum.characterization.quantumphaseestimation> operazione, che accetta un' <xref:microsoft.quantum.oracles.discreteoracle> applicazione di implementazione di $U ^ m $ come funzione di numeri interi positivi $m $.
