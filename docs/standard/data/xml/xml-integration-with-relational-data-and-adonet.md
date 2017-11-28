---
title: "XML integrace s relačních dat a ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6ebb1a1-f2ca-49b9-92c9-0150940cf6e6
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5d03a0ca7518b06c08d98967d7c5ae864f1c04ac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="xml-integration-with-relational-data-and-adonet"></a><span data-ttu-id="04ade-102">XML integrace s relačních dat a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="04ade-102">XML Integration with Relational Data and ADO.NET</span></span>
<span data-ttu-id="04ade-103">**XmlDataDocument** třída je třídu odvozenou z **třídou XMLDocument nastavenou na**a obsahuje XML data.</span><span class="sxs-lookup"><span data-stu-id="04ade-103">The **XmlDataDocument** class is a derived class of the **XmlDocument**, and contains XML data.</span></span> <span data-ttu-id="04ade-104">Výhodou **XmlDataDocument** je, že zajišťuje most mezi hierarchické a relační data.</span><span class="sxs-lookup"><span data-stu-id="04ade-104">The advantage of the **XmlDataDocument** is that it provides a bridge between relational and hierarchical data.</span></span> <span data-ttu-id="04ade-105">Je **třídou XMLDocument nastavenou na** mohou být vázány na **datovou sadu** a obě třídy můžete synchronizovat změny provedené data obsažená ve dvou tříd.</span><span class="sxs-lookup"><span data-stu-id="04ade-105">It is an **XmlDocument** that can be bound to a **DataSet** and both classes can synchronize changes made to data contained in the two classes.</span></span> <span data-ttu-id="04ade-106">**Třídou XMLDocument nastavenou na** která je vázaná **datovou sadu** umožňuje XML tak, aby integrovat relačních dat, a není nutné mít data reprezentována jako buď XML nebo v relačním formátu.</span><span class="sxs-lookup"><span data-stu-id="04ade-106">An **XmlDocument** that is bound to a **DataSet** allows XML to integrate with relational data, and you do not have to have your data represented as either XML or in a relational format.</span></span> <span data-ttu-id="04ade-107">Můžete provést i a nesmí být omezené na jednom znázornění dat.</span><span class="sxs-lookup"><span data-stu-id="04ade-107">You can do both and not be constrained to a single representation of the data.</span></span>  
  
 <span data-ttu-id="04ade-108">Výhod, které nejsou k dispozici ve dvou zobrazení data jsou:</span><span class="sxs-lookup"><span data-stu-id="04ade-108">The benefits of having data available in two views are:</span></span>  
  
-   <span data-ttu-id="04ade-109">Strukturované část dokumentu XML lze mapovat na datovou sadu a efektivně ukládat, indexované a vyhledávat.</span><span class="sxs-lookup"><span data-stu-id="04ade-109">The structured portion of an XML document can be mapped to a dataset, and be efficiently stored, indexed, and searched.</span></span>  
  
-   <span data-ttu-id="04ade-110">Transformace, ověřování a navigační lze provést efektivně prostřednictvím modelu kurzoru přes data XML, která je uložená relationally.</span><span class="sxs-lookup"><span data-stu-id="04ade-110">Transformations, validation, and navigation can be done efficiently through a cursor model over the XML data that is stored relationally.</span></span> <span data-ttu-id="04ade-111">V některých případech je možné ji provést efektivněji proti relační struktury než pokud XML je uložen v **třídou XMLDocument nastavenou na** modelu.</span><span class="sxs-lookup"><span data-stu-id="04ade-111">At times, it can be done more efficiently against relational structures than if the XML is stored in an **XmlDocument** model.</span></span>  
  
-   <span data-ttu-id="04ade-112">**Datovou sadu** můžete uložit část XML.</span><span class="sxs-lookup"><span data-stu-id="04ade-112">The **DataSet** can store a portion of the XML.</span></span> <span data-ttu-id="04ade-113">To znamená, že můžete použít **XPath** nebo **XslTransform** k uložení do **datovou sadu** pouze elementy a atributy, které vás zajímají.</span><span class="sxs-lookup"><span data-stu-id="04ade-113">That is, you can use **XPath** or **XslTransform** to store to a **DataSet** only those elements and attributes of interest.</span></span> <span data-ttu-id="04ade-114">Odtud můžete provedeny změny menší, která jsou filtrovaná podmnožinu dat, se změnami šíření větší data ve **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="04ade-114">From there, changes can be made to the smaller, filtered subset of data, with the changes propagating to the larger data in the **XmlDataDocument**.</span></span>  
  
 <span data-ttu-id="04ade-115">Můžete taky spustit transformace přes data, která byla načtena do **datovou sadu** ze serveru SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04ade-115">You can also run a transform over data that was loaded into the **DataSet** from SQL Server.</span></span> <span data-ttu-id="04ade-116">Další možností je vytvořit vazbu WinForm spravované styl třídy rozhraní .NET Framework a pro ovládací prvky webových formulářů **datovou sadu** , se naplní ze vstupní datový proud XML.</span><span class="sxs-lookup"><span data-stu-id="04ade-116">Another option is to bind .NET Framework classes-style-managed WinForm and WebForm controls to a **DataSet** that was populated from an XML input stream.</span></span>  
  
 <span data-ttu-id="04ade-117">Vedle podpory **XslTransform**, **XmlDataDocument** zpřístupní relační data **XPath** dotazy a ověření.</span><span class="sxs-lookup"><span data-stu-id="04ade-117">In addition to supporting **XslTransform**, an **XmlDataDocument** exposes relational data to **XPath** queries and validation.</span></span>  <span data-ttu-id="04ade-118">V podstatě všechny XML služby jsou dostupné přes relačních dat a relační zařízení, jako je vazba ovládacího prvku, codegen atd., jsou k dispozici prostřednictvím strukturovaných projekce XML bez kompromisů věrnosti XML.</span><span class="sxs-lookup"><span data-stu-id="04ade-118">Basically, all XML services are available over relational data, and relational facilities, such as control binding, codegen, and so on, are available over a structured projection of XML without compromising XML fidelity.</span></span>  
  
 <span data-ttu-id="04ade-119">Protože **XmlDataDocument** je zděděn z **třídou XMLDocument nastavenou na**, poskytuje implementaci W3C modelu DOM.</span><span class="sxs-lookup"><span data-stu-id="04ade-119">Because **XmlDataDocument** is inherited from an **XmlDocument**, it provides an implementation of the W3C DOM.</span></span> <span data-ttu-id="04ade-120">Fakt, **XmlDataDocument** je přidružen k nim a ukládá podmnožinu jeho data v rámci, **datovou sadu** neomezuje nebo změnit jeho použití jako **třídou XMLDocument nastavenou na** žádným způsobem.</span><span class="sxs-lookup"><span data-stu-id="04ade-120">The fact that the **XmlDataDocument** is associated with, and stores a subset of its data within, a **DataSet** does not restrict or alter its use as an **XmlDocument** in any way.</span></span> <span data-ttu-id="04ade-121">Kód zapisovaný využívat **třídou XMLDocument nastavenou na** funguje v nezměněném stavu proti **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="04ade-121">Code written to consume an **XmlDocument** works unaltered against an **XmlDataDocument**.</span></span> <span data-ttu-id="04ade-122">**Datovou sadu** poskytuje relační zobrazení dat tak, že definujete tabulek, sloupců, vztahy a omezení a je úložiště dat, které uživatel samostatnou, v paměti.</span><span class="sxs-lookup"><span data-stu-id="04ade-122">The **DataSet** provides the relational view of the same data by defining tables, columns, relations, and constraints, and is a stand-alone, in-memory user data store.</span></span>  
  
 <span data-ttu-id="04ade-123">Následující obrázek znázorňuje jiné přidružení, že má XML data s **datovou sadu** a **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="04ade-123">The following illustration shows the different associations that XML data has with the **DataSet** and **XmlDataDocument**.</span></span>  
  
 <span data-ttu-id="04ade-124">![Datová sada XML](../../../../docs/standard/data/xml/media/xmlintegrationwithrelationaldataandadodotnet.gif "xmlIntegrationWithRelationalDataAndADOdotNet")</span><span class="sxs-lookup"><span data-stu-id="04ade-124">![XML DataSet](../../../../docs/standard/data/xml/media/xmlintegrationwithrelationaldataandadodotnet.gif "xmlIntegrationWithRelationalDataAndADOdotNet")</span></span>  
  
 <span data-ttu-id="04ade-125">Na obrázku vidíte, že je možné načíst XML data přímo do **datovou sadu**, což umožňuje přímé manipulaci se souborem XML relační způsobem.</span><span class="sxs-lookup"><span data-stu-id="04ade-125">The illustration shows that XML data can be loaded directly into a **DataSet**, which allows direct manipulation with XML in the relational manner.</span></span> <span data-ttu-id="04ade-126">Nebo, XML, je možné načíst do odvozené třídy modelu DOM, který je **XmlDataDocument**a následně načíst a synchronizována s **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="04ade-126">Or, the XML can be loaded into a derived class of the DOM, which is the **XmlDataDocument**, and subsequently loaded and synchronized with the **DataSet**.</span></span> <span data-ttu-id="04ade-127">Protože **datovou sadu** a **XmlDataDocument** jsou synchronizovány v rámci jedné sady dat, se projeví změny provedené v datech v jedno úložiště v jiného úložiště.</span><span class="sxs-lookup"><span data-stu-id="04ade-127">Because the **DataSet** and **XmlDataDocument** are synchronized over a single set of data, changes made to the data in one store are reflected in the other store.</span></span>  
  
 <span data-ttu-id="04ade-128">**XmlDataDocument** dědí všechny úpravy a navigační funkce z **třídou XMLDocument nastavenou na**.</span><span class="sxs-lookup"><span data-stu-id="04ade-128">The **XmlDataDocument** inherits all the editing and navigational features from the **XmlDocument**.</span></span> <span data-ttu-id="04ade-129">V určitých časech při použití **XmlDataDocument** a jeho zděděné funkce synchronizovat se službou **datovou sadu**, je vhodnější možnost než načtení XML přímo do **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="04ade-129">There are times when using the **XmlDataDocument** and its inherited features, synchronized with a **DataSet**, is a more appropriate option than loading XML directly into the **DataSet**.</span></span> <span data-ttu-id="04ade-130">V následující tabulce jsou uvedeny položky, které mají být považovány za při výběru, kterou metodu použít k načtení **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="04ade-130">The following table shows the items to be considered when choosing which method to use to load the **DataSet**.</span></span>  
  
|<span data-ttu-id="04ade-131">Pokud k načtení XML přímo do datové sady</span><span class="sxs-lookup"><span data-stu-id="04ade-131">When to load XML directly into a DataSet</span></span>|<span data-ttu-id="04ade-132">Při synchronizaci XmlDataDocument s datové sady</span><span class="sxs-lookup"><span data-stu-id="04ade-132">When to synchronize an XmlDataDocument with a DataSet</span></span>|  
|----------------------------------------------|-----------------------------------------------------------|  
|<span data-ttu-id="04ade-133">Dotazy dat v **datovou sadu** se snadněji pomocí SQL než XPath.</span><span class="sxs-lookup"><span data-stu-id="04ade-133">Queries of data in the **DataSet** are easier using SQL than XPath.</span></span>|<span data-ttu-id="04ade-134">Dotazy XPath jsou potřeba nad daty v **datovou sadu**.</span><span class="sxs-lookup"><span data-stu-id="04ade-134">XPath queries are needed over data in the **DataSet**.</span></span>|  
|<span data-ttu-id="04ade-135">Zachování elementu řazení ve zdroji XML není důležité.</span><span class="sxs-lookup"><span data-stu-id="04ade-135">Preservation of element ordering in the source XML is not critical.</span></span>|<span data-ttu-id="04ade-136">Zachování elementu řazení ve zdroji XML je velmi důležité.</span><span class="sxs-lookup"><span data-stu-id="04ade-136">Preservation of element ordering in the source XML is critical.</span></span>|  
|<span data-ttu-id="04ade-137">Mezer mezi elementy a formátování nemusí být zachována ve zdroji XML.</span><span class="sxs-lookup"><span data-stu-id="04ade-137">White space between elements and formatting does not need to be preserved in the source XML.</span></span>|<span data-ttu-id="04ade-138">Prázdné znaky a formátování zachovávání ve zdroji XML je velmi důležité.</span><span class="sxs-lookup"><span data-stu-id="04ade-138">White space and formatting preservation in the source XML is critical.</span></span>|  
  
 <span data-ttu-id="04ade-139">Pokud načtení a zápis XML přímo do a z **datovou sadu** adresy vašim potřebám, najdete v části [načítání datové sady z XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) a [zápis datovou sadu jako XML Data](../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="04ade-139">If loading and writing XML directly into and out of a **DataSet** addresses your needs, see [Loading a DataSet from XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) and [Writing a DataSet as XML Data](../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="04ade-140">Pokud načítání **datovou sadu** z **XmlDataDocument** adresy vašim potřebám, najdete v části [synchronizace Datasetwith dokument XML](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="04ade-140">If loading the **DataSet** from an **XmlDataDocument** addresses your needs, see [Synchronizing a Datasetwith an XML Document](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ade-141">Viz také</span><span class="sxs-lookup"><span data-stu-id="04ade-141">See Also</span></span>  
 [<span data-ttu-id="04ade-142">Pomocí XML v datové sadě</span><span class="sxs-lookup"><span data-stu-id="04ade-142">Using XML in a DataSet</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)