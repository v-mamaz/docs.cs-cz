---
title: Literál XML CDATA (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 01a505130d566ec88a6d87e5e9ad525e449d7298
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981241"
---
# <a name="xml-cdata-literal-visual-basic"></a>Literál XML CDATA (Visual Basic)
Literál představující <xref:System.Xml.Linq.XCData> objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Součásti  
 `<![CDATA[`  
 Povinný parametr. Označuje začátek oddílu CDATA kódu XML.  
  
 `content`  
 Povinný parametr. Textový obsah se zobrazí v oddílu CDATA kódu XML.  
  
 `]]>`  
 Povinný parametr. Označuje konec oddílu.  
  
## <a name="return-value"></a>Návratová hodnota  
 <xref:System.Xml.Linq.XCData> Objektu.  
  
## <a name="remarks"></a>Poznámky  
 XML CDATA oddíly obsahují nezpracovaný text, který by měl zahrnuty, ale nebyly analyzovány pomocí XML, který jej obsahuje. Oddíl CDATA kódu XML může obsahovat libovolný text. To zahrnuje vyhrazené znaky jazyka XML. Sekce XML CDATA končí sekvence "]] >". Z toho vyplývá následující body:  
  
-   V XML CDATA, který je literál nejde použít vložený výraz, protože vložený výraz oddělovače jsou platný obsah XML CDATA.  
  
-   XML CDATA oddíly nelze vnořit, protože `content` nemůže obsahovat hodnotu "]] >".  
  
 Můžete přiřadit literál XML CDATA proměnné nebo zahrnout do literálů XML element.  
  
> [!NOTE]
>  Literál XML může zahrnovat více řádků, ale nepoužívá znaky pokračování řádku. To umožňuje kopírovat obsah z dokumentu XML a vložte ho přímo do programu Visual Basic.  
  
 Kompilátor jazyka Visual Basic převede literál XML CDATA na volání <xref:System.Xml.Linq.XCData.%23ctor%2A> konstruktoru.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří oddíl CDATA, který obsahuje text "může obsahovat literál \<XML > značky".  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Xml.Linq.XCData>
- [Literál XML elementu](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literály XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Vytvoření XML v jazyce Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
