---
title: Technologie LINQ to XML Annotations2
ms.date: 07/20/2015
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
ms.openlocfilehash: 891c451bc573e41e26833878187224cf54510435
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566846"
---
# <a name="linq-to-xml-annotations"></a>Technologie LINQ to XML poznámky
Poznámky v [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vám umožní přidružit libovolné součásti XML ve stromu XML libovolného objektu jakéhokoli libovolného typu.  
  
 Přidat poznámku komponentě XML, jako například <xref:System.Xml.Linq.XElement> nebo <xref:System.Xml.Linq.XAttribute>, volání <xref:System.Xml.Linq.XObject.AddAnnotation%2A> metody. Načtení poznámek podle typu.  
  
 Všimněte si, že poznámky nejsou součástí informační sadu XML; nejsou serializován nebo deserializován.  
  
## <a name="methods"></a>Metody  
 Při práci s poznámkami, můžete použít následující metody:  
  
|Metoda|Popis|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Přidá objekt do seznamu poznámky <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|Získá první anotace objekt zadaného typu ze <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|Získá kolekci poznámek zadaného typu pro <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Odebere poznámky zadaného typu ze <xref:System.Xml.Linq.XObject>.|  
  
## <a name="see-also"></a>Viz také:
- [Pokročilé technologie LINQ to XML programování (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
