---
title: Určení funkcí důležitost modely s důležitostí permutaci funkce v ML.NET
description: Pochopení důležitosti funkce modelů s důležitostí permutaci funkce v ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b0457bc07168579403e5a00383864c5612e1d17f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675547"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a>Určení funkcí důležitost modely s důležitostí permutaci funkce v ML.NET

> [!NOTE]
> Toto téma odkazuje na ML.NET, která je aktuálně ve verzi Preview, a materiálu se můžou stát terčem změnit. Další informace najdete v článku [Úvod ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Aktuálně používáte této ukázky s postupy a související **ML.NET verze 0.10**. Další informace najdete v tématu poznámky k verzi v [úložiště GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Při vytváření modelů strojového učení, nestačí často stačí provést předpovědi. Vývojáři, pracovníci s rozhodovací pravomocí a jsou ovlivněny modely strojového učení často, potřebujete pochopit, jak se rozhodovat modelů strojového učení a funkcí, které přispívají k jejich výkon. `Permutation Feature Importance` (PFI) je nástroj explainability modelu, který se používá interně v Microsoftu, což vývojářům umožňuje machine learning lepší pochopení důležitosti funkce modelů.

PFI je technika, chcete-li zjistit **globální funkce význam** v modelu trénovaného strojového učení, motivováno Breiman v ["Random doménových struktur" papír, část 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf). PFI měří funkce význam položením otázky, "co vliv na model bude-li hodnoty pro funkci byly nastaveny na náhodnou * hodnotu?". Výhodou PFI metody je, že je nezávislý na modelu – funguje to pro všechny modely, které lze vyhodnotit – a všech datových sadách, ne jenom cvičnou sadou, může použít k výpočtu důležité funkce. Vám pomůže PFI jako tak vytvořit importances funkci jako tento graf:

![Graf funkce význam permutaci](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model.LastTransformer, model.Transform(data), "MedianHomeValue");

// Get the feature names from the training set
var featureNames =
    data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Write out the feature names and their importance to the model's Mean R-squared value
for (int i = 0; i < featureNames.Length;i++)
{
    Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].RSquared.Mean:G4}");
}
```

Příklad použití PFI k analýze funkce důležitost modelu, naleznete v tématu [úložiště GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).

/ * I, ne náhodné přesně, ale permutovanou funkci mezi několik příkladů.
