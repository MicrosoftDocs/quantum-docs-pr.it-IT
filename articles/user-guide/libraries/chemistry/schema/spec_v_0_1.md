---
title: Specifica dello schema Broombridge (ver 0,1)
description: Vengono illustrate in dettaglio le specifiche per Broombridge Quantum Chemistry Schema v 0.1 per Microsoft Quantum Chemistry Library.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276043"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="a8aab-103">Specifica Broombridge v 0.1</span><span class="sxs-lookup"><span data-stu-id="a8aab-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="a8aab-104">Le parole chiave "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDed", "MAY" e "OPTIONAL" in questo documento devono essere interpretate come descritto nella [specifica RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="a8aab-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="a8aab-105">Qualsiasi sidebar con le intestazioni "NOTE", "informazioni" o "avviso" è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="a8aab-106">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a8aab-106">Introduction</span></span> ##

<span data-ttu-id="a8aab-107">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-107">This section is informative.</span></span>

<span data-ttu-id="a8aab-108">I documenti Broombridge sono destinati a comunicare istanze di problemi di simulazione nella chimica quantistica per l'elaborazione usando la simulazione quantistica e la programmazione toolchain.</span><span class="sxs-lookup"><span data-stu-id="a8aab-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="a8aab-109">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="a8aab-109">Serialization</span></span> ##

<span data-ttu-id="a8aab-110">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-110">This section is normative.</span></span>

<span data-ttu-id="a8aab-111">Un documento Broombridge deve essere serializzato come [documento YAML 1,2](http://yaml.org/spec/) che rappresenta un oggetto JSON, come descritto in [RFC 4627](https://tools.ietf.org/html/rfc4627) Section 2,2.</span><span class="sxs-lookup"><span data-stu-id="a8aab-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="a8aab-112">L'oggetto serializzato per YAML deve avere una proprietà il `"$schema"` cui valore è `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` e deve essere valido in base alle specifiche bozza-06 dello schema JSON [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="a8aab-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="a8aab-113">Per la parte restante di questa specifica, "l'oggetto Broombridge" si riferisce all'oggetto JSON deserializzato da un documento YAML di Broombridge.</span><span class="sxs-lookup"><span data-stu-id="a8aab-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="a8aab-114">Se non diversamente specificato in modo esplicito, gli oggetti non devono avere proprietà aggiuntive oltre a quelle specificate in modo esplicito in questo documento.</span><span class="sxs-lookup"><span data-stu-id="a8aab-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="a8aab-115">Definizioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a8aab-115">Additional Definitions</span></span> ##

<span data-ttu-id="a8aab-116">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="a8aab-117">Quantità-oggetti</span><span class="sxs-lookup"><span data-stu-id="a8aab-117">Quantity Objects</span></span> ###

<span data-ttu-id="a8aab-118">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-118">This section is normative.</span></span>

<span data-ttu-id="a8aab-119">Un _oggetto Quantity_ è un oggetto JSON e deve avere una proprietà `units` il cui valore è uno dei valori consentiti elencati nella tabella 1.</span><span class="sxs-lookup"><span data-stu-id="a8aab-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="a8aab-120">Un oggetto Quantity è un _oggetto quantità semplice_ se dispone di una singola proprietà `value` oltre alla relativa `units` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8aab-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="a8aab-121">Il valore della `value` proprietà deve essere un numero.</span><span class="sxs-lookup"><span data-stu-id="a8aab-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="a8aab-122">Un oggetto Quantity è un _oggetto quantità delimitata_ se dispone delle proprietà `lower` e `upper` in aggiunta alla relativa `units` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8aab-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="a8aab-123">I valori delle `lower` proprietà e `upper` devono essere numeri.</span><span class="sxs-lookup"><span data-stu-id="a8aab-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="a8aab-124">Un oggetto della quantità limitata può avere una proprietà il `value` cui valore è un numero.</span><span class="sxs-lookup"><span data-stu-id="a8aab-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="a8aab-125">Un oggetto Quantity è un _oggetto Quantity della matrice di tipo sparse_ se dispone della proprietà `format` e di una proprietà `values` oltre alla relativa `units` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8aab-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="a8aab-126">Il valore di `format` deve essere la stringa `sparse` .</span><span class="sxs-lookup"><span data-stu-id="a8aab-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="a8aab-127">Il valore della `values` proprietà deve essere una matrice.</span><span class="sxs-lookup"><span data-stu-id="a8aab-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="a8aab-128">Ogni elemento di `values` deve essere una matrice che rappresenta gli indici e il valore della quantità di matrici di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="a8aab-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="a8aab-129">Gli indici per ogni elemento di un oggetto della quantità di matrici di tipo sparse devono essere univoci nell'intero oggetto della quantità di matrici di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="a8aab-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="a8aab-130">Se è presente un indice con un valore di `0` , un parser deve trattare l'oggetto quantità di matrici di tipo sparse in modo identico a un oggetto quantità di matrici di tipo sparse in cui tale indice non è presente.</span><span class="sxs-lookup"><span data-stu-id="a8aab-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="a8aab-131">Un oggetto Quantity deve essere</span><span class="sxs-lookup"><span data-stu-id="a8aab-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="a8aab-132">un oggetto quantità semplice,</span><span class="sxs-lookup"><span data-stu-id="a8aab-132">a simple quantity object,</span></span>
- <span data-ttu-id="a8aab-133">oggetto della quantità delimitata o</span><span class="sxs-lookup"><span data-stu-id="a8aab-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="a8aab-134">oggetto della quantità di matrici di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="a8aab-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="a8aab-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8aab-135">Examples</span></span> ###

<span data-ttu-id="a8aab-136">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-136">This section is informative.</span></span>

<span data-ttu-id="a8aab-137">Una quantità semplice che rappresenta $1.9844146837 \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="a8aab-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="a8aab-138">Una quantità limitata che rappresenta una distribuzione uniforme nell'intervallo $ [-7,-6] \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="a8aab-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="a8aab-139">Di seguito è riportata una quantità di matrici di tipo sparse con un elemento `[1, 2]` uguale a `hello` e un elemento `[3, 4]` uguale a `world` :</span><span class="sxs-lookup"><span data-stu-id="a8aab-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="a8aab-140">Sezione Format</span><span class="sxs-lookup"><span data-stu-id="a8aab-140">Format Section</span></span> ##

<span data-ttu-id="a8aab-141">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-141">This section is normative.</span></span>

<span data-ttu-id="a8aab-142">L'oggetto Broombridge deve avere una proprietà il `format` cui valore è un oggetto JSON con una proprietà denominata `version` .</span><span class="sxs-lookup"><span data-stu-id="a8aab-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="a8aab-143">Il `version` valore della proprietà deve essere `"0.1"` .</span><span class="sxs-lookup"><span data-stu-id="a8aab-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="a8aab-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8aab-144">Example</span></span> ###

<span data-ttu-id="a8aab-145">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="a8aab-146">Sezione set integrali</span><span class="sxs-lookup"><span data-stu-id="a8aab-146">Integral Sets Section</span></span> ##

<span data-ttu-id="a8aab-147">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-147">This section is normative.</span></span>

<span data-ttu-id="a8aab-148">L'oggetto Broombridge deve avere una proprietà il `integral_sets` cui valore è una matrice JSON.</span><span class="sxs-lookup"><span data-stu-id="a8aab-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="a8aab-149">Ogni elemento del valore della `integral_sets` proprietà deve essere un oggetto JSON che descrive un set di integrali, come descritto nella parte restante di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a8aab-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="a8aab-150">Nella parte restante di questa sezione, il termine "oggetto set integrale" fa riferimento a un elemento nel valore della `integral_sets` proprietà dell'oggetto Broombridge.</span><span class="sxs-lookup"><span data-stu-id="a8aab-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="a8aab-151">Ogni oggetto set integrale deve avere una proprietà il `metadata` cui valore è un oggetto JSON.</span><span class="sxs-lookup"><span data-stu-id="a8aab-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="a8aab-152">Il valore di `metadata` può essere l'oggetto JSON vuoto (ovvero `{}` ) oppure può contenere proprietà aggiuntive definite dall'implementatore.</span><span class="sxs-lookup"><span data-stu-id="a8aab-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="a8aab-153">Sezione hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="a8aab-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="a8aab-154">Panoramica</span><span class="sxs-lookup"><span data-stu-id="a8aab-154">Overview</span></span> ####

<span data-ttu-id="a8aab-155">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-155">This section is informative.</span></span>

<span data-ttu-id="a8aab-156">La `hamiltonian` proprietà di ogni oggetto set integrale descrive l'Hamiltoniana per un particolare problema di chimica quantistica elencando i termini di uno e due corpi come matrici di tipo sparse di numeri reali.</span><span class="sxs-lookup"><span data-stu-id="a8aab-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="a8aab-157">Gli operatori hamiltoniana descritti da ogni oggetto set integrale hanno il formato</span><span class="sxs-lookup"><span data-stu-id="a8aab-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="a8aab-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} h \_ \{ IJ \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in {\uparrow \\ , \downarrow \\ }} h \_ {IJKL} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="a8aab-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="a8aab-159">qui $h _ {IJKL} = (IJ | KL) $ nella convenzione Mulliken.</span><span class="sxs-lookup"><span data-stu-id="a8aab-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="a8aab-160">Per maggiore chiarezza, il termine a un elettrone è</span><span class="sxs-lookup"><span data-stu-id="a8aab-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="a8aab-161">$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ a} {| x-x \_ A |}  \right) \psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="a8aab-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="a8aab-162">e il termine a due elettroni è</span><span class="sxs-lookup"><span data-stu-id="a8aab-162">and the two-electron term is</span></span>

<span data-ttu-id="a8aab-163">$ $ h \_ \{ IJKL \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="a8aab-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="a8aab-164">Come indicato nella descrizione della [ `basis_set` Proprietà](#basis-set-object) di ogni elemento della `integral_sets` proprietà, si presuppone in modo esplicito che le funzioni di base usate siano di valore reale.</span><span class="sxs-lookup"><span data-stu-id="a8aab-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="a8aab-165">In questo modo è possibile usare le simmetrie seguenti tra i termini per comprimere la rappresentazione dell'hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="a8aab-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="a8aab-166">$ $ h_ {IJKL} = h_ {Ijlk} = h_ {jikl} = h_ {JILK} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="a8aab-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="a8aab-167">Contenuto</span><span class="sxs-lookup"><span data-stu-id="a8aab-167">Contents</span></span> ####

<span data-ttu-id="a8aab-168">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-168">This section is normative.</span></span>

<span data-ttu-id="a8aab-169">Ogni set integrale deve avere una proprietà il `hamiltonian` cui valore è un oggetto JSON.</span><span class="sxs-lookup"><span data-stu-id="a8aab-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="a8aab-170">Il valore della `hamiltonian` proprietà è noto come oggetto Hamiltoniana e deve avere le proprietà `one_electron_integrals` e `two_electron_integrals` come descritto nella parte restante di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a8aab-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="a8aab-171">Un oggetto hamiltoniana può anche avere una proprietà `particle_hole_representation` .</span><span class="sxs-lookup"><span data-stu-id="a8aab-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="a8aab-172">Se presente, il valore di `particle_hole_representation` deve rispettare il formato descritto nella parte rimanente di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a8aab-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="a8aab-173">Oggetto integrali a un elettrone</span><span class="sxs-lookup"><span data-stu-id="a8aab-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="a8aab-174">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-174">This section is normative.</span></span>

<span data-ttu-id="a8aab-175">La `one_electron_integrals` proprietà dell'oggetto HAMILTONIANA deve essere una quantità di matrici di tipo sparse i cui indici sono due interi e i cui valori sono numeri.</span><span class="sxs-lookup"><span data-stu-id="a8aab-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="a8aab-176">Ogni termine deve avere indici `[i, j]` dove `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="a8aab-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="a8aab-177">Si noti Riflette la simmetria che $h _ {IJ} = h_ {ji} $, che è una conseguenza del fatto che l'hamiltoniana è Hermitiane.</span><span class="sxs-lookup"><span data-stu-id="a8aab-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="a8aab-178">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8aab-178">Example</span></span> ######

<span data-ttu-id="a8aab-179">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-179">This section is informative.</span></span>

<span data-ttu-id="a8aab-180">La seguente quantità di matrici di tipo sparse rappresenta l'oggetto hamiltoniana $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="a8aab-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="a8aab-181">Broombridge usa l'indicizzazione in base 1.</span><span class="sxs-lookup"><span data-stu-id="a8aab-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="a8aab-182">Oggetto integrali a due elettroni</span><span class="sxs-lookup"><span data-stu-id="a8aab-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="a8aab-183">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-183">This section is normative.</span></span>

<span data-ttu-id="a8aab-184">La `two_electron_integrals` proprietà dell'oggetto HAMILTONIANA deve essere una quantità di matrici di tipo sparse con una proprietà aggiuntiva denominata `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="a8aab-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="a8aab-185">Ogni elemento del valore di `two_electron_integrals` deve avere quattro indici.</span><span class="sxs-lookup"><span data-stu-id="a8aab-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="a8aab-186">Ogni `two_electron_integrals` proprietà deve avere una `index_convention` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8aab-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="a8aab-187">Il valore della `index_convention` proprietà deve essere uno dei valori consentiti elencati nella tabella 1.</span><span class="sxs-lookup"><span data-stu-id="a8aab-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="a8aab-188">Se il valore di `index_convention` è `mulliken` , per ogni elemento della quantità di `two_electron_integrals` matrici di tipo sparse, un parser che carica un documento Broombridge deve creare un'istanza di un termine hamiltoniana uguale all'operatore a due elettroni $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_L $, dove $i $, $j $, $k $ e $l $ devono essere numeri interi nell'intervallo inclusivo compreso tra 1 e il numero di elettroni specificati dalla `n_electrons` proprietà dell'oggetto set integrale e dove $h _ {i, j, k, l} $ è l'elemento `[i, j, k, l, h(i, j, k, l)]` della quantità di matrici di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="a8aab-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="a8aab-189">Simmetrie</span><span class="sxs-lookup"><span data-stu-id="a8aab-189">Symmetries</span></span> ######

<span data-ttu-id="a8aab-190">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-190">This section is normative.</span></span>

<span data-ttu-id="a8aab-191">Se la `index_convention` proprietà di un `two_electron_integrals` oggetto è uguale a `mulliken` , se è presente un elemento con indici `[i, j, k, l]` , gli indici seguenti non devono essere presenti, a meno che non siano uguali a `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="a8aab-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="a8aab-192">Poiché la `index_convention` proprietà è un oggetto di quantità sparse, nessun indici può essere ripetuto su elementi diversi.</span><span class="sxs-lookup"><span data-stu-id="a8aab-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="a8aab-193">In particolare, se è presente un elemento con indici `[i, j, k, l]` , nessun altro elemento può avere tali indici.</span><span class="sxs-lookup"><span data-stu-id="a8aab-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="a8aab-194">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8aab-194">Example</span></span> #######

<span data-ttu-id="a8aab-195">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-195">This section is informative.</span></span>

<span data-ttu-id="a8aab-196">L'oggetto seguente specifica l'Hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="a8aab-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="a8aab-197">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="a8aab-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="a8aab-198">Particella-oggetto rappresentazione Hole</span><span class="sxs-lookup"><span data-stu-id="a8aab-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="a8aab-199">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-199">This section is normative.</span></span>

<span data-ttu-id="a8aab-200">L'oggetto rappresentazione particella-Hole specifica che gli integrali archiviati sono definiti rispetto alla rappresentazione del foro particella, in cui gli operatori di creazione e di annientamento descrivono le eccitazioni dallo stato di riferimento usato, ad esempio uno stato Hartree-Fock.</span><span class="sxs-lookup"><span data-stu-id="a8aab-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="a8aab-201">L'oggetto è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a8aab-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="a8aab-202">Se l'oggetto non viene specificato, l'Hamiltoniana deve essere interpretato come non specificato nella rappresentazione del foro particellare.</span><span class="sxs-lookup"><span data-stu-id="a8aab-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="a8aab-203">Se presente, il valore di `particle_hole_representation` deve essere un oggetto quantità di matrici di tipo sparse i cui indici sono quattro numeri interi e i cui valori sono un numero e una stringa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="a8aab-204">La parte di stringa del valore di ogni elemento deve contenere solo i caratteri `'+'` e `'-'` che specifica se un determinato fattore nel termine è un operatore di creazione o di annientamento nella rappresentazione particellare-foro.</span><span class="sxs-lookup"><span data-stu-id="a8aab-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="a8aab-205">Ad esempio `"-+++"` , corisponde a un foro creato nel sito $i $ e particelle create nei siti $j, k $ e $l $.</span><span class="sxs-lookup"><span data-stu-id="a8aab-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="a8aab-206">Poiché il valore di `particle_hole_representation` è un oggetto quantità di matrici di tipo sparse, è `unit` `format` necessario specificare le proprietà e.</span><span class="sxs-lookup"><span data-stu-id="a8aab-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="a8aab-207">Le unità accettabili includono elencate nella tabella 1.</span><span class="sxs-lookup"><span data-stu-id="a8aab-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="a8aab-208">La `format` proprietà è obbligatoria e indica se i coefficienti hamiltoniana vengono specificati come una matrice densa o di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="a8aab-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="a8aab-209">Nella versione corrente sono supportate solo le matrici di tipo sparse, con l'interpretazione che tutti gli elementi non specificati sono $0 $, ma le versioni future possono aggiungere il supporto per i valori aggiuntivi della `format` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8aab-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="a8aab-210">Sezione stato iniziale</span><span class="sxs-lookup"><span data-stu-id="a8aab-210">Initial State Section</span></span> ###

<span data-ttu-id="a8aab-211">L'oggetto initial_state_suggestion specifica gli Stati del quantum iniziale di interesse per l'Hamiltoniana specificata.</span><span class="sxs-lookup"><span data-stu-id="a8aab-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="a8aab-212">Questo oggetto deve essere una matrice di `state` oggetti JSON.</span><span class="sxs-lookup"><span data-stu-id="a8aab-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="a8aab-213">State (oggetto)</span><span class="sxs-lookup"><span data-stu-id="a8aab-213">State object</span></span> ####

<span data-ttu-id="a8aab-214">Ogni stato rappresenta una sovrapposizione di orbite occupate.</span><span class="sxs-lookup"><span data-stu-id="a8aab-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="a8aab-215">Ogni oggetto stato deve avere una `label` proprietà che contiene una stringa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="a8aab-216">Ogni oggetto stato deve avere una `superposition` proprietà contenente una matrice di Stati di base e le relative ampiezze non normalizzate.</span><span class="sxs-lookup"><span data-stu-id="a8aab-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="a8aab-217">Ad esempio, gli stati iniziali $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0.2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} $ $ sono rappresentate da</span><span class="sxs-lookup"><span data-stu-id="a8aab-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="a8aab-218">Oggetto set di basi</span><span class="sxs-lookup"><span data-stu-id="a8aab-218">Basis Set Object</span></span> ####

<span data-ttu-id="a8aab-219">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-219">This section is normative.</span></span>

<span data-ttu-id="a8aab-220">Ogni oggetto set integrale può avere una `basis_set` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8aab-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="a8aab-221">Se presente, il valore della `basis_set` proprietà deve essere un oggetto con due proprietà, `type` e `name` .</span><span class="sxs-lookup"><span data-stu-id="a8aab-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="a8aab-222">Le funzioni di base identificate dal valore della `basis_set` proprietà devono essere con valori reali.</span><span class="sxs-lookup"><span data-stu-id="a8aab-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="a8aab-223">Il presupposto che tutte le funzioni di base siano a valore reale possono essere rilassate nelle versioni future di questa specifica.</span><span class="sxs-lookup"><span data-stu-id="a8aab-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="a8aab-224">Tabelle ed elenchi</span><span class="sxs-lookup"><span data-stu-id="a8aab-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="a8aab-225">Tabella 1.</span><span class="sxs-lookup"><span data-stu-id="a8aab-225">Table 1.</span></span> <span data-ttu-id="a8aab-226">Unità fisiche consentite</span><span class="sxs-lookup"><span data-stu-id="a8aab-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="a8aab-227">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-227">This section is normative.</span></span>

<span data-ttu-id="a8aab-228">Qualsiasi stringa che specifica un'unità deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8aab-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="a8aab-229">I parser e i producer devono considerare come equivalenti gli oggetti della quantità semplice seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8aab-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="a8aab-230">Tabella 2.</span><span class="sxs-lookup"><span data-stu-id="a8aab-230">Table 2.</span></span> <span data-ttu-id="a8aab-231">Convenzioni di indice consentite</span><span class="sxs-lookup"><span data-stu-id="a8aab-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="a8aab-232">Questa sezione è normativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-232">This section is normative.</span></span>

<span data-ttu-id="a8aab-233">Qualsiasi stringa che specifica una convenzione di indice deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8aab-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="a8aab-234">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-234">This section is informative.</span></span>

<span data-ttu-id="a8aab-235">Le convenzioni di indice aggiuntive possono essere introdotte nelle versioni future di questa specifica.</span><span class="sxs-lookup"><span data-stu-id="a8aab-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="a8aab-236">Interpretazione delle convenzioni degli indici</span><span class="sxs-lookup"><span data-stu-id="a8aab-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="a8aab-237">Questa sezione è informativa.</span><span class="sxs-lookup"><span data-stu-id="a8aab-237">This section is informative.</span></span>
