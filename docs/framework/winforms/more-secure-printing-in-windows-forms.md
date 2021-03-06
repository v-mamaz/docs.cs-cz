---
title: Bezpečnější tisk ve Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 2fd61ea1c56ee2dbe7ff725d9f9f79df6b6cdfd8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723032"
---
# <a name="more-secure-printing-in-windows-forms"></a>Bezpečnější tisk ve Windows Forms
Aplikace Windows Forms často přinášejí tisk schopnosti. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Používá <xref:System.Drawing.Printing.PrintingPermission> třídy pro řízení přístupu k funkcím, tisk a přidružené <xref:System.Drawing.Printing.PrintingPermissionLevel> hodnota výčtu označující úroveň přístupu. Ve výchozím nastavení je ve výchozím nastavení do zóny místního intranetu a Internetu; povolené tisk úroveň přístupu je však omezeny v obou oblastech. Zda lze vytisknout vaší aplikace, vyžaduje zásah uživatele, nebo nelze tisk závisí na hodnotě oprávnění udělených aplikaci. Ve výchozím nastavení, obdrží zóny místního intranetu <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> přístup a zóny intranetu obdrží <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> přístup.  
  
 V následující tabulce jsou uvedeny funkce, která je dostupná na všech úrovních tisk oprávnění.  
  
|PrintingPermissionLevel|Popis|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Poskytuje úplný přístup ke všem nainstalovaných tiskáren.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Umožňuje tisk prostřednictvím kódu programu, použije se výchozí tiskárna a bezpečnější tisk přes omezující tisk dialogového okna. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> je podmnožinou <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Poskytuje pouze z více omezený dialogové okno Tisk. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> je podmnožinou <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Brání v přístupu k tiskárny. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> je podmnožinou <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Viz také:
- [Zabezpečenější přístup k souborům a datům ve Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)
- [Dodatečné informace o zabezpečení ve Windows Forms](additional-security-considerations-in-windows-forms.md)
- [Přehled zabezpečení ve Windows Forms](security-in-windows-forms-overview.md)
- [Windows Forms – zabezpečení](windows-forms-security.md)
