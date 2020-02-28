---
title: Caricamento di dati classici
description: Informazioni su come caricare un set di dati personalizzato per eseguire il training di un modello di classificazione con il Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: 15e63ced6223759a332ce22a43c133a7899f482a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909960"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="1581e-103">Caricare e classificare i propri set di impostazioni</span><span class="sxs-lookup"><span data-stu-id="1581e-103">Load and classify your own datasets</span></span>

<span data-ttu-id="1581e-104">In questa breve esercitazione si apprenderà come caricare un set di dati personalizzato per eseguire il training di un modello di classificazione con Quantum Development Kit (QDK).</span><span class="sxs-lookup"><span data-stu-id="1581e-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="1581e-105">È consigliabile usare un formato di serializzazione standardizzato, ad esempio [file JSON](https://en.wikipedia.org/wiki/JSON) , per archiviare i dati.</span><span class="sxs-lookup"><span data-stu-id="1581e-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="1581e-106">Questi formati offrono una compatibilità elevata con Framework diversi come Python e l'ecosistema .NET.</span><span class="sxs-lookup"><span data-stu-id="1581e-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="1581e-107">In particolare, è consigliabile usare il modello per il caricamento dei dati, in modo che sia possibile copiare e incollare il codice direttamente dagli esempi.</span><span class="sxs-lookup"><span data-stu-id="1581e-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="1581e-108">Modello per il caricamento dei set di impostazioni</span><span class="sxs-lookup"><span data-stu-id="1581e-108">Template for loading your datasets</span></span>

<span data-ttu-id="1581e-109">Si supponga di avere un set di dati di training $ (x, y) $ of size $N = $2, in cui ogni istanza $x _i $ of $x $ include tre funzionalità: $x _ {I1} $, $x _ {I2} $ e $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="1581e-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="1581e-110">Il set di dati di convalida ha la stessa struttura.</span><span class="sxs-lookup"><span data-stu-id="1581e-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="1581e-111">Questi set possono essere rappresentati da un file `data.json` simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1581e-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a><span data-ttu-id="1581e-112">Esempio di utilizzo del modello</span><span class="sxs-lookup"><span data-stu-id="1581e-112">Example using the template</span></span>

<span data-ttu-id="1581e-113">Si supponga di avere un set di dati di piccole dimensioni con le altezze e i pesi dei diversi gatti e cani.</span><span class="sxs-lookup"><span data-stu-id="1581e-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="1581e-114">Questo set di dati è molto piccolo per eseguire il training di un modello, ma sarà sufficiente per illustrare il processo di caricamento di un set di dati.</span><span class="sxs-lookup"><span data-stu-id="1581e-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="1581e-115">Altezza (m)</span><span class="sxs-lookup"><span data-stu-id="1581e-115">Height (m)</span></span> | <span data-ttu-id="1581e-116">Peso (kg)</span><span class="sxs-lookup"><span data-stu-id="1581e-116">Weight (kg)</span></span> | <span data-ttu-id="1581e-117">Animale</span><span class="sxs-lookup"><span data-stu-id="1581e-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="1581e-118">0,54</span><span class="sxs-lookup"><span data-stu-id="1581e-118">0.54</span></span>      | <span data-ttu-id="1581e-119">30</span><span class="sxs-lookup"><span data-stu-id="1581e-119">30</span></span>         | <span data-ttu-id="1581e-120">Cane</span><span class="sxs-lookup"><span data-stu-id="1581e-120">Dog</span></span>    |
| <span data-ttu-id="1581e-121">0,30</span><span class="sxs-lookup"><span data-stu-id="1581e-121">0.30</span></span>      | <span data-ttu-id="1581e-122">8</span><span class="sxs-lookup"><span data-stu-id="1581e-122">8</span></span>          | <span data-ttu-id="1581e-123">Gatto</span><span class="sxs-lookup"><span data-stu-id="1581e-123">Cat</span></span>    |
| <span data-ttu-id="1581e-124">0,91</span><span class="sxs-lookup"><span data-stu-id="1581e-124">0.91</span></span>      | <span data-ttu-id="1581e-125">44</span><span class="sxs-lookup"><span data-stu-id="1581e-125">44</span></span>         | <span data-ttu-id="1581e-126">Cane</span><span class="sxs-lookup"><span data-stu-id="1581e-126">Dog</span></span>    |
| <span data-ttu-id="1581e-127">0,86</span><span class="sxs-lookup"><span data-stu-id="1581e-127">0.86</span></span>      | <span data-ttu-id="1581e-128">31</span><span class="sxs-lookup"><span data-stu-id="1581e-128">31</span></span>          | <span data-ttu-id="1581e-129">Cane</span><span class="sxs-lookup"><span data-stu-id="1581e-129">Dog</span></span>    |
| <span data-ttu-id="1581e-130">0,32</span><span class="sxs-lookup"><span data-stu-id="1581e-130">0.32</span></span>      | <span data-ttu-id="1581e-131">5</span><span class="sxs-lookup"><span data-stu-id="1581e-131">5</span></span>         | <span data-ttu-id="1581e-132">Gatto</span><span class="sxs-lookup"><span data-stu-id="1581e-132">Cat</span></span>    |
| <span data-ttu-id="1581e-133">0,25</span><span class="sxs-lookup"><span data-stu-id="1581e-133">0.25</span></span>      | <span data-ttu-id="1581e-134">4</span><span class="sxs-lookup"><span data-stu-id="1581e-134">4</span></span>          | <span data-ttu-id="1581e-135">Gatto</span><span class="sxs-lookup"><span data-stu-id="1581e-135">Cat</span></span>    |

<span data-ttu-id="1581e-136">Il processo è:</span><span class="sxs-lookup"><span data-stu-id="1581e-136">The process is:</span></span>

- <span data-ttu-id="1581e-137">Per prima cosa, è necessario separare il set di dati in training e convalida.</span><span class="sxs-lookup"><span data-stu-id="1581e-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="1581e-138">In questo caso, è possibile adottare solo i primi tre esempi per il training e il resto degli esempi per la convalida.</span><span class="sxs-lookup"><span data-stu-id="1581e-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="1581e-139">In generale, è consigliabile campionare in modo casuale il set di dati di training e convalida per evitare distorsioni indesiderate nei dati di training.</span><span class="sxs-lookup"><span data-stu-id="1581e-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="1581e-140">In secondo luogo, è necessario assegnare un'etichetta numerica a ogni classe.</span><span class="sxs-lookup"><span data-stu-id="1581e-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="1581e-141">Si noti che, per il momento, la libreria QML ammette solo problemi di classificazione binaria.</span><span class="sxs-lookup"><span data-stu-id="1581e-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="1581e-142">Si assegnerà quindi l'etichetta 0 alla classe `Dog` e il numero 1 alla classe `Cat`.</span><span class="sxs-lookup"><span data-stu-id="1581e-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="1581e-143">Infine, il modello viene compilato usando i dati del set di dati.</span><span class="sxs-lookup"><span data-stu-id="1581e-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="1581e-144">Si noti che per i set di dati di grandi dimensioni è necessario compilare uno script di piccole dimensioni per generare automaticamente il modello dal set di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="1581e-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="1581e-145">Lo script dipenderà dal formato originale del set di dati.</span><span class="sxs-lookup"><span data-stu-id="1581e-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="1581e-146">Per il set di dati, il file `data.json` è:</span><span class="sxs-lookup"><span data-stu-id="1581e-146">For our dataset the `data.json` file is:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a><span data-ttu-id="1581e-147">Caricamento dei dati</span><span class="sxs-lookup"><span data-stu-id="1581e-147">Loading the data</span></span>

<span data-ttu-id="1581e-148">Una volta che i dati sono stati serializzati come file JSON, è possibile caricarli in usando le librerie JSON fornite con la lingua host scelta.</span><span class="sxs-lookup"><span data-stu-id="1581e-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="1581e-149">Python</span><span class="sxs-lookup"><span data-stu-id="1581e-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="1581e-150">Python fornisce il [pacchetto di `json` incorporato](https://docs.python.org/3.7/library/json.html) per l'uso di dati serializzati in JSON:</span><span class="sxs-lookup"><span data-stu-id="1581e-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="1581e-151">C#</span><span class="sxs-lookup"><span data-stu-id="1581e-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="1581e-152">La piattaforma .NET Core fornisce il [pacchetto di`System.Text.Json`](https://www.nuget.org/packages/System.Text.Json) per l'uso di dati serializzati in JSON:</span><span class="sxs-lookup"><span data-stu-id="1581e-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="whats-next"></a><span data-ttu-id="1581e-153">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="1581e-153">What's next?</span></span>

<span data-ttu-id="1581e-154">A questo punto è possibile iniziare a eseguire i propri esperimenti con i propri set di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1581e-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="1581e-155">Prova diversi classificatori e set di dati e contribuisci alla community che condivide i risultati.</span><span class="sxs-lookup"><span data-stu-id="1581e-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
