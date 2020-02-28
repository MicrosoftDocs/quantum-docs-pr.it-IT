---
title: Specifica dello schema Broombridge (ver 0,1)
description: Vengono illustrate in dettaglio le specifiche per Broombridge Quantum Chemistry Schema v 0.1 per Microsoft Quantum Chemistry Library.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906424"
---
# <a name="broombridge-specification-v01"></a>Specifica Broombridge v 0.1 #

Le parole chiave "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDed", "MAY" e "OPTIONAL" in questo documento devono essere interpretate come descritto nella [specifica RFC 2119](https://tools.ietf.org/html/rfc2119).

Qualsiasi sidebar con le intestazioni "NOTE", "informazioni" o "avviso" è informativa.

## <a name="introduction"></a>Introduzione ##

Questa sezione è informativa.

I documenti Broombridge sono destinati a comunicare istanze di problemi di simulazione nella chimica quantistica per l'elaborazione usando la simulazione quantistica e la programmazione toolchain.

## <a name="serialization"></a>Serializzazione ##

Questa sezione è normativa.

Un documento Broombridge deve essere serializzato come [documento YAML 1,2](http://yaml.org/spec/) che rappresenta un oggetto JSON, come descritto in [RFC 4627](https://tools.ietf.org/html/rfc4627) Section 2,2.
L'oggetto serializzato per YAML deve avere una proprietà `"$schema"` il cui valore è `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`e deve essere valido in base alle specifiche bozza-06 dello schema JSON [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Per la parte restante di questa specifica, "l'oggetto Broombridge" si riferisce all'oggetto JSON deserializzato da un documento YAML di Broombridge.

Se non diversamente specificato in modo esplicito, gli oggetti non devono avere proprietà aggiuntive oltre a quelle specificate in modo esplicito in questo documento.

## <a name="additional-definitions"></a>Definizioni aggiuntive ##

Questa sezione è normativa.

### <a name="quantity-objects"></a>Quantità-oggetti ###

Questa sezione è normativa.

Un _oggetto Quantity_ è un oggetto JSON e deve avere una proprietà `units` il cui valore è uno dei valori consentiti elencati nella tabella 1.

Un oggetto Quantity è un _oggetto quantità semplice_ se dispone di una singola proprietà `value` oltre alla relativa proprietà `units`.
Il valore della proprietà `value` deve essere un numero.

Un oggetto Quantity è un _oggetto Quantity associato_ se dispone delle proprietà `lower` e `upper` oltre alla relativa proprietà `units`.
I valori delle proprietà `lower` e `upper` devono essere numeri.
Un oggetto della quantità limitata può avere una proprietà `value` il cui valore è un numero.

Un oggetto Quantity è un _oggetto quantità di matrici di tipo sparse_ se ha la proprietà `format` e una proprietà `values` oltre alla relativa proprietà `units`.
Il valore di `format` deve essere la stringa `sparse`.
Il valore della proprietà `values` deve essere una matrice.
Ogni elemento di `values` deve essere una matrice che rappresenta gli indici e il valore della quantità di matrici di tipo sparse.

Gli indici per ogni elemento di un oggetto della quantità di matrici di tipo sparse devono essere univoci nell'intero oggetto della quantità di matrici di tipo sparse.
Se è presente un indice con un valore di `0`, un parser deve considerare l'oggetto quantità di matrici di tipo sparse in modo identico a un oggetto quantità di matrici di tipo sparse in cui tale indice non è presente.


Un oggetto Quantity deve essere

- un oggetto quantità semplice,
- oggetto della quantità delimitata o
- oggetto della quantità di matrici di tipo sparse.


### <a name="examples"></a>Esempi ###

Questa sezione è informativa.

Quantità semplice che rappresenta $1.9844146837\,\mathrm{Ha} $:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Una quantità limitata che rappresenta una distribuzione uniforme nell'intervallo $ [-7,-6]\,\mathrm{Ha} $:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Di seguito è riportata una quantità di matrici di tipo sparse con un elemento `[1, 2]` uguale a `hello` e un elemento `[3, 4]` uguale a `world`:

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Sezione Format ##

Questa sezione è normativa.

L'oggetto Broombridge deve avere una proprietà `format` il cui valore è un oggetto JSON con una proprietà denominata `version`.
Il valore della proprietà `version` deve essere `"0.1"`.

### <a name="example"></a>Esempio ###

Questa sezione è informativa.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Sezione set integrali ##

Questa sezione è normativa.

L'oggetto Broombridge deve avere una proprietà `integral_sets` il cui valore è una matrice JSON.
Ogni elemento del valore della proprietà `integral_sets` deve essere un oggetto JSON che descrive un set di integrali, come descritto nella parte restante di questa sezione.
Nella parte restante di questa sezione, il termine "oggetto set integrale" fa riferimento a un elemento nel valore della proprietà `integral_sets` dell'oggetto Broombridge.

Ogni oggetto set integrale deve avere una proprietà `metadata` il cui valore è un oggetto JSON.
Il valore di `metadata` può essere l'oggetto JSON vuoto (ovvero `{}`) oppure può contenere proprietà aggiuntive definite dall'implementatore.

### <a name="hamiltonian-section"></a>Sezione hamiltoniana ###

#### <a name="overview"></a>Panoramica ####

Questa sezione è informativa.

La proprietà `hamiltonian` di ogni oggetto set integrale descrive l'Hamiltoniana per un particolare problema di chimica quantistica elencando i termini di uno e due corpi come matrici di tipo sparse di numeri reali.
Gli operatori hamiltoniana descritti da ogni oggetto set integrale hanno il formato

$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} h\_\{IJ\} a ^\{\dagger\}\_{i, \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{IJKL} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

qui $h _ {IJKL} = (IJ | KL) $ nella convenzione Mulliken.

Per maggiore chiarezza, il termine a un elettrone è

$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ *\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $

e il termine a due elettroni è

$ $ h\_\{IJKL\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).
$$

Come indicato nella descrizione della [proprietà`basis_set`](#basis-set-object) di ogni elemento della proprietà `integral_sets`, si presuppone in modo esplicito che le funzioni di base usate siano di valore reale.
In questo modo è possibile usare le simmetrie seguenti tra i termini per comprimere la rappresentazione dell'hamiltoniana.

$ $ h_ {IJKL} = h_ {Ijlk} = h_ {jikl} = h_ {JILK} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>Sommario ####

Questa sezione è normativa.

Ogni set integrale deve avere una proprietà `hamiltonian` il cui valore è un oggetto JSON.
Il valore della proprietà `hamiltonian` è noto come oggetto hamiltoniana ed è necessario che le proprietà `one_electron_integrals` e `two_electron_integrals` come descritto nella parte restante di questa sezione.
Un oggetto hamiltoniana può anche avere una proprietà `particle_hole_representation`.
Se presente, il valore di `particle_hole_representation` deve rispettare il formato descritto nella parte rimanente di questa sezione.

##### <a name="one-electron-integrals-object"></a>Oggetto integrali a un elettrone #####

Questa sezione è normativa.

La proprietà `one_electron_integrals` dell'oggetto hamiltoniana deve essere una quantità di matrici di tipo sparse i cui indici sono due Integer e i cui valori sono numeri.
Ogni termine deve avere indici `[i, j]` in cui `i >= j`.

> Si noti Riflette la simmetria che $h _ {IJ} = h_ {ji} $, che è una conseguenza del fatto che l'hamiltoniana è Hermitiane.


###### <a name="example"></a>Esempio ######

Questa sezione è informativa.

La seguente quantità di matrici di tipo sparse rappresenta l'oggetto hamiltoniana $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1, \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> Broombridge usa l'indicizzazione in base 1.


##### <a name="two-electron-integrals-object"></a>Oggetto integrali a due elettroni #####

Questa sezione è normativa.

La proprietà `two_electron_integrals` dell'oggetto hamiltoniana deve essere una quantità di matrici di tipo sparse con una proprietà aggiuntiva denominata `index_convention`.
Ogni elemento del valore di `two_electron_integrals` deve avere quattro indici.

Ogni proprietà `two_electron_integrals` deve avere una proprietà `index_convention`.
Il valore della proprietà `index_convention` deve essere uno dei valori consentiti elencati nella tabella 1.
Se il valore di `index_convention` è `mulliken`, per ogni elemento della quantità `two_electron_integrals` matrice di tipo sparse, un parser che carica un documento Broombridge deve creare un'istanza di un termine hamiltoniana uguale all'operatore a due elettroni $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, dove $i $, $j $, $k $ e $l $ devono essere numeri interi nell'intervallo inclusivo compreso tra 1 e il numero di elettroni specificati dalla proprietà `n_electrons` dell'oggetto set integrale e dove $h _ {i, j , k, l} $ è l'elemento `[i, j, k, l, h(i, j, k, l)]` della quantità di matrici di tipo sparse.

###### <a name="symmetries"></a>Simmetrie ######

Questa sezione è normativa.

Se la proprietà `index_convention` di un oggetto `two_electron_integrals` è uguale a `mulliken`, se è presente un elemento con indici `[i, j, k, l]`, gli indici seguenti non devono essere presenti, a meno che non siano uguali a `[i, j, k, l]`:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Poiché la proprietà `index_convention` è un oggetto quantità di tipo sparse, non è possibile ripetere gli indici su elementi diversi.
> In particolare, se è presente un elemento con indici `[i, j, k, l]`, nessun altro elemento potrà avere tali indici.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Esempio #######

Questa sezione è informativa.

L'oggetto seguente specifica l'Hamiltoniana

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2 , \rho} a\_{3, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2, \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3 , \sigma} a ^ {\dagger}\_{2, \rho} a\_{1, \rho} a\_{6 \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

##### <a name="particlehole-representation-object"></a>Particella-oggetto rappresentazione Hole #####

Questa sezione è normativa.

L'oggetto rappresentazione particella-Hole specifica che gli integrali archiviati sono definiti rispetto alla rappresentazione del foro particella, in cui gli operatori di creazione e di annientamento descrivono le eccitazioni dallo stato di riferimento usato, ad esempio Hartree- Stato Fock.
L'oggetto è facoltativo.
Se l'oggetto non viene specificato, l'Hamiltoniana deve essere interpretato come non specificato nella rappresentazione del foro particellare.
Se presente, il valore di `particle_hole_representation` deve essere un oggetto Quantity della matrice di tipo sparse i cui indici sono quattro numeri interi e i cui valori sono un numero e una stringa.
La parte stringa del valore di ogni elemento deve contenere solo i caratteri `'+'` e `'-'` che specifica se un determinato fattore nel termine è un operatore di creazione o di annientamento nella rappresentazione particellare-foro.  Ad esempio `"-+++"` corisponde a un foro creato al sito $i $ e alle particelle create nei siti $j, k $ e $l $.

> [!NOTE]
> Poiché il valore della `particle_hole_representation` è un oggetto quantità di matrici di tipo sparse, è necessario specificare le proprietà `unit` e `format`.
> Le unità accettabili includono elencate nella tabella 1.
> La proprietà `format` è obbligatoria e indica se i coefficienti hamiltoniana vengono specificati come una matrice densa o di tipo sparse.
> Nella versione corrente sono supportate solo le matrici di tipo sparse, con l'interpretazione che tutti gli elementi non specificati sono $0 $, ma le versioni future possono aggiungere il supporto per i valori aggiuntivi della proprietà `format`.

### <a name="initial-state-section"></a>Sezione stato iniziale ###

L'oggetto initial_state_suggestion specifica gli Stati del quantum iniziale di interesse per l'Hamiltoniana specificata. Questo oggetto deve essere una matrice di oggetti JSON `state`.

#### <a name="state-object"></a>State (oggetto) ####

Ogni stato rappresenta una sovrapposizione di orbite occupate. Ogni oggetto stato deve avere una proprietà `label` contenente una stringa. Ogni oggetto stato deve avere una proprietà `superposition` contenente una matrice di Stati di base e le relative ampiezze non normalizzate.

Ad esempio, gli stati iniziali $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0.2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0} $ $ sono rappresentati da
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a>Oggetto set di basi ####

Questa sezione è normativa.

Ogni oggetto set integrale può avere una proprietà `basis_set`.
Se presente, il valore della proprietà `basis_set` deve essere un oggetto con due proprietà, `type` e `name`.

Le funzioni di base identificate dal valore della proprietà `basis_set` devono essere con valori reali.

> [!NOTE]
> Il presupposto che tutte le funzioni di base siano a valore reale possono essere rilassate nelle versioni future di questa specifica.

## <a name="tables-and-lists"></a>Tabelle ed elenchi ##

### <a name="table-1-allowed-physical-units"></a>Tabella 1. Unità fisiche consentite ###

Questa sezione è normativa.

Qualsiasi stringa che specifica un'unità deve essere una delle seguenti:

- `hartree`
- `ev`

I parser e i producer devono considerare come equivalenti gli oggetti della quantità semplice seguenti:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tabella 2. Convenzioni di indice consentite ###

Questa sezione è normativa.

Qualsiasi stringa che specifica una convenzione di indice deve essere una delle seguenti:

- `mulliken`

Questa sezione è informativa.

Le convenzioni di indice aggiuntive possono essere introdotte nelle versioni future di questa specifica.

#### <a name="interpretation-of-index-conventions"></a>Interpretazione delle convenzioni degli indici ####

Questa sezione è informativa.
