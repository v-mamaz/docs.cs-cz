---
title: Přehled názvových prostorů (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
ms.openlocfilehash: b2ea4c28fe14e57d3f72bb29d4960f436bbd9bb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603696"
---
# <a name="namespaces-overview-linq-to-xml"></a>Přehled názvových prostorů (LINQ to XML)
Toto téma představuje obory názvů, <xref:System.Xml.Linq.XName> třídy a <xref:System.Xml.Linq.XNamespace> třídy.  
  
## <a name="xml-names"></a>Názvy XML  
 Názvy XML jsou často zdroj složitosti XML programování. Název XML obsahuje obor názvů XML (také nazývané identifikátor URI oboru názvů XML) a místní název. Obor názvů XML je podobný v oboru názvů [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-programu. Umožňuje vám k vyfiltrování jedinečné názvy prvků a atributů. To pomáhá předejít název je v konfliktu mezi různé části dokumentu XML. Když je deklarován obor názvů XML, můžete vybrat místní název, který se musí být jedinečný v rámci tohoto oboru názvů.  
  
 Dalším aspektem názvy XML je XML *předpony oboru názvů*. XML předpony způsobit, že většina složitost názvy XML. Tyto předpony umožňují vytvořit zástupce pro obor názvů XML, který vytvoří dokument XML, výstižný a srozumitelný. XML předpony však závisí na jejich kontextu má význam, který zvyšuje složitost. Například, předpona XML `aw` asociované s jeden obor názvů XML v jedné části stromu XML a jiný obor názvů XML v jiné části stromu XML.  
  
 Při použití [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] s literály jazyka Visual Basic a XML, je nutné použít předpony oboru názvů při práci s dokumenty v oborech názvů.  
  
 V [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], je třída, která představuje názvy XML <xref:System.Xml.Linq.XName>. Názvy XML se zobrazí často v průběhu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] rozhraní API, a bez ohledu na to se vyžaduje název XML, najdete <xref:System.Xml.Linq.XName> parametru. Ale zřídka pracovat přímo se <xref:System.Xml.Linq.XName>. <xref:System.Xml.Linq.XName> obsahuje implicitní převod z řetězce.  
  
 Další informace naleznete v tématu <xref:System.Xml.Linq.XNamespace> a <xref:System.Xml.Linq.XName>.  
  
## <a name="see-also"></a>Viz také:
- [Práce s názvovými prostory XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
