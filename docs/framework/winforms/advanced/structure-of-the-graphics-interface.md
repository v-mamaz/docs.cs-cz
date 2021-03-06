---
title: Struktura rozhraní grafiky
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: 33be9d4d4e5a1aca933bb84e948b2200cd96b152
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708107"
---
# <a name="structure-of-the-graphics-interface"></a>Struktura rozhraní grafiky
Spravované třídy rozhraní [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] obsahuje přibližně 60 třídy, 50 výčty a struktury 8. <xref:System.Drawing.Graphics> Třída je v jádru služby [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funkce; je třída, která ve skutečnosti kreslí řádky, křivek, obrázky, obrázky a text.  
  
## <a name="important-classes"></a>Důležité třídy  
 Mnoho tříd pracovat společně <xref:System.Drawing.Graphics> třídy. Například <xref:System.Drawing.Graphics.DrawLine%2A> metoda přijímá <xref:System.Drawing.Pen> objektu, který obsahuje atributy (barvu, šířku, zpřístupní Styl přerušování a podobně) chcete kreslit čáry. <xref:System.Drawing.Graphics.FillRectangle%2A> Metoda může přijímat ukazatel <xref:System.Drawing.Drawing2D.LinearGradientBrush> objektu, který funguje s <xref:System.Drawing.Graphics> objektu tak, aby vyplnil obdélník postupně měnící barvou. <xref:System.Drawing.Font> a <xref:System.Drawing.StringFormat> objekty ovlivňují způsob <xref:System.Drawing.Graphics> objektu kreslení textu. A <xref:System.Drawing.Drawing2D.Matrix> objekt ukládá a manipuluje s Světové transformace <xref:System.Drawing.Graphics> objektu, který se používá k otočení, škálování a překlopit bitové kopie.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] poskytuje několik struktury (například <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, a <xref:System.Drawing.Size>) pro uspořádání dat grafiky. Také určité třídy slouží především strukturované datové typy. Například <xref:System.Drawing.Imaging.BitmapData> třída je pomocné rutiny pro <xref:System.Drawing.Bitmap> třídy a <xref:System.Drawing.Drawing2D.PathData> třída je pomocné rutiny pro <xref:System.Drawing.Drawing2D.GraphicsPath> třídy.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] definuje několik výčty, které jsou kolekce související s konstantami. Například <xref:System.Drawing.Drawing2D.LineJoin> výčet obsahuje prvky <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, a <xref:System.Drawing.Drawing2D.LineJoin.Round>, která zadejte stylů, které je možné připojit dva řádky.  
  
## <a name="see-also"></a>Viz také:
- [Přehled grafiky](graphics-overview-windows-forms.md)
- [Informace o spravovaném kódu GDI+](about-gdi-managed-code.md)
- [Použití spravovaných grafických tříd](using-managed-graphics-classes.md)
