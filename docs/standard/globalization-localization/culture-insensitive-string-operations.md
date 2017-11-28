---
title: "Operace s řetězci nezávislé na jazykových verzích"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET Framework], culture-insensitive string operations
- strings [.NET Framework], culture-insensitive string operations
- localization [.NET Framework], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dddd46dc5d825738dd9d5038ae573910122953c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="culture-insensitive-string-operations"></a><span data-ttu-id="bde58-102">Operace s řetězci nezávislé na jazykových verzích</span><span class="sxs-lookup"><span data-stu-id="bde58-102">Culture-Insensitive String Operations</span></span>
<span data-ttu-id="bde58-103">Operace s řetězci závislé na jazykové verzi mohou být vhodné v případě, že vytváříte aplikace, které jsou navrhovány tak, aby uživatelům zobrazovaly výsledky na základě jazykové verze.</span><span class="sxs-lookup"><span data-stu-id="bde58-103">Culture-sensitive string operations can be an advantage if you are creating applications designed to display results to users on a per-culture basis.</span></span> <span data-ttu-id="bde58-104">Ve výchozím nastavení, metody závislé získat jazykovou verzi pro použití z <xref:System.Globalization.CultureInfo.CurrentCulture%2A> vlastnost pro aktuální vlákno.</span><span class="sxs-lookup"><span data-stu-id="bde58-104">By default, culture-sensitive methods obtain the culture to use from the <xref:System.Globalization.CultureInfo.CurrentCulture%2A> property for the current thread.</span></span>  
  
 <span data-ttu-id="bde58-105">Pamatujte, že operace s řetězci závislé na jazykové verzi nemusí vždy představovat požadované chování.</span><span class="sxs-lookup"><span data-stu-id="bde58-105">Note that culture-sensitive string operations are not always the desired behavior.</span></span> <span data-ttu-id="bde58-106">Používání operací závislých na jazykové verzi v případě, že výsledky by měly být na jazykové verzi nezávislé, může způsobit selhání kódu aplikace v jazykových verzích s vlastními pravidly mapování a řazení.</span><span class="sxs-lookup"><span data-stu-id="bde58-106">Using culture-sensitive operations when results should be independent of culture can cause application code to fail on cultures with custom case mappings and sorting rules.</span></span> <span data-ttu-id="bde58-107">Příklad, najdete v části "Řetězec porovnání, použijte aktuální jazykovou verzi" v [osvědčené postupy pro používání řetězců](../../../docs/standard/base-types/best-practices-strings.md) článku.</span><span class="sxs-lookup"><span data-stu-id="bde58-107">For an example, see the "String Comparisons that Use the Current Culture" section in the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article.</span></span>  
  
 <span data-ttu-id="bde58-108">Skutečnost, zda operace s řetězci mají být závislé nebo nezávislé na jazykové verzi, závisí na tom, jakým způsobem aplikace pracuje s výsledky.</span><span class="sxs-lookup"><span data-stu-id="bde58-108">Whether string operations should be culture-sensitive or culture-insensitive depends on how your application uses the results.</span></span> <span data-ttu-id="bde58-109">Operace s řetězci, které zobrazují výsledky uživateli, by měly být většinou závislé na jazykové verzi.</span><span class="sxs-lookup"><span data-stu-id="bde58-109">String operations that display results to the user should typically be culture-sensitive.</span></span> <span data-ttu-id="bde58-110">Pokud například konkrétní aplikace zobrazuje seřazený seznam lokalizovaných řetězců v seznamu, měla by aplikace provést řazení závislé na jazykové verzi.</span><span class="sxs-lookup"><span data-stu-id="bde58-110">For example, if an application displays a sorted list of localized strings in a list box, the application should perform a culture-sensitive sort.</span></span>  
  
 <span data-ttu-id="bde58-111">Výsledky operací s řetězci, které se používají interně, by měly být většinou nezávislé na jazykové verzi.</span><span class="sxs-lookup"><span data-stu-id="bde58-111">Results of string operations that are used internally should typically be culture-insensitive.</span></span> <span data-ttu-id="bde58-112">Obecně platí, že pokud aplikace pracuje s názvy souborů, formáty persistence nebo symbolickými informacemi, které se uživateli nezobrazují, neměly by se výsledky operací s řetězci lišit podle jazykové verze.</span><span class="sxs-lookup"><span data-stu-id="bde58-112">In general, if the application is working with file names, persistence formats, or symbolic information that is not displayed to the user, results of string operations should not vary by culture.</span></span> <span data-ttu-id="bde58-113">Pokud aplikace například porovnává řetězec a chce určit, zda se jedná o rozpoznanou značku XML, porovnání by nemělo být závislé na jazykové verzi.</span><span class="sxs-lookup"><span data-stu-id="bde58-113">For example, if an application compares a string to determine whether it is a recognized XML tag, the comparison should not be culture-sensitive.</span></span> <span data-ttu-id="bde58-114">Kromě toho pokud rozhodnutí zabezpečení je založená na výsledek operace s řetězci porovnání nebo případ změnu, operace by měla být nezávislé na jazykových zajistit, že výsledek není ovlivněn hodnotu <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.</span><span class="sxs-lookup"><span data-stu-id="bde58-114">In addition, if a security decision is based on the result of a string comparison or case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.</span></span>  
  
 <span data-ttu-id="bde58-115">Bez ohledu na to, zda vyvíjíte aplikaci, která obsahuje kód pro zpracování problémů lokalizace a globalizace, měli byste si být vědomi metod rozhraní .NET Framework, které automaticky získávají výsledky závislé na jazykové verzi.</span><span class="sxs-lookup"><span data-stu-id="bde58-115">Whether or not you are developing an application that includes code to handle localization and globalization issues, you should be aware of the .NET Framework methods that retrieve culture-sensitive results by default.</span></span> <span data-ttu-id="bde58-116">Účelem tohoto tématu je objasnění správného způsobu používání těchto metod v rámci aplikací pro získávání výsledků nezávislých na jazykové verzi.</span><span class="sxs-lookup"><span data-stu-id="bde58-116">The purpose of this topic is to illustrate the correct way for your applications to use these methods to obtain culture-insensitive results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bde58-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="bde58-117">See Also</span></span>  
 [<span data-ttu-id="bde58-118">Globalizace a lokalizace</span><span class="sxs-lookup"><span data-stu-id="bde58-118">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)