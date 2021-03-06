---
title: Chyby při návrhu v Návrháři formulářů Windows
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
ms.openlocfilehash: 64a0b8d0d0d9f0cc2bc2a841b999af58f29b4f75
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718048"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a>Chyby při návrhu v Návrháři formulářů Windows
Toto téma vysvětluje význam a použití seznamu chyb při návrhu, který se zobrazí v sadě Microsoft Visual Studio, když Návrhář formulářů Windows nepodaří načíst. Pokud se zobrazí tento seznam chyb, by neměla interpretovat jako chyba v návrháři, ale jako pomůcka pro opravu chyb v kódu.  
  
 Základní znalosti o tento seznam chyb můžete ladit aplikace tak, že poskytuje podrobné informace o chybách a navrhněte řešení.  
  
## <a name="the-design-time-error-list-interface"></a>Rozhraní seznam chyb při návrhu  
 Pokud se nepodaří načíst Návrháře formulářů Windows, seznamu chyb se zobrazí v návrháři. Chyby jsou seskupené do kategorií. Například pokud máte čtyři instance nedeklarované proměnné, ty budou seskupeny do stejné kategorie chyby. Každá kategorie chyby obsahuje stručný popis, který shrnuje chybu.  
  
 Můžete rozbalit nebo Sbalit kategorii chyby, kliknutím na záhlaví kategorie chyby nebo kliknutím na dvojitou šipku Rozbalit/sbalit. Když rozbalíte kategorii chyby, zobrazí se následující další pomoc:  
  
-   Instance této chyby.  
  
-   Nápověda k této chybě.  
  
-   Fórum příspěvky o této chybě.  
  
### <a name="instances-of-this-error"></a>Instance této chyby  
 Další nápověda seznam všech instancí chybu v aktuálním projektu. Mnoho chyb obsahovat přesné umístění v následujícím formátu: *[název projektu]* *[název formuláře]* řádku:*[číslo]* sloupec:*– sloupec číslo*. **Přejít ke kódu** odkaz vás nasměruje na umístění ve vašem kódu, kde dojde k chybě.  
  
 Pokud zásobníku volání je spojen s chybou, můžete kliknout **zobrazit zásobník volání** propojení, které dále rozšiřujících chyby, chcete-li zobrazit zásobník volání. Zkoumání zásobník může poskytnout cenné informace o ladění. Můžete například sledovat, funkce, které byly volány předtím, než došlo k chybě. Zásobník volání je volitelný, takže můžete zkopírovat a uložit ho.  
  
> [!NOTE]
>  V jazyce Visual Basic v seznamu chyb při návrhu nezobrazí více než jednu chybu, ale může zobrazovat více instancí stejné chybě. Chyby v aplikaci Visual C++, nemají goto code odkazy nebo odkazy na čísla řádku.  
  
### <a name="help-with-this-error"></a>Nápověda k této chybě  
 Pokud chyba obsahuje odkaz na související téma nápovědy MSDN, další pomoc bude obsahovat odkaz na téma nápovědy. Když kliknete na odkaz, zobrazí se v sadě Visual Studio související téma nápovědy.  
  
### <a name="forum-posts-about-this-error"></a>Fórum příspěvky o této chybě  
 Další pomoc, bude obsahovat odkaz na příspěvků na fórech MSDN týkající se chyby. Fóra budou vyhledány podle řetězec chybové zprávy. Můžete také zkusit hledání následující fóra:  
  
-   [Fórum Návrháře formulářů Windows](https://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [Windows Forms fóra](https://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a>Ignorovat a pokračovat  
 Můžete ignorovat chybovou podmínku a pokračovat v načítání návrháře. Výběrem této akce může způsobit neočekávané chování. Například ovládací prvky se nemusí zobrazit na návrhové ploše.  
  
## <a name="see-also"></a>Viz také:
- [Řešení potíží s vývojem během návrhu](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
- [Řešení potíží s vytvářením ovládacích prvků a komponent](troubleshooting-control-and-component-authoring.md)
- [Vývoj ovládacích prvků Windows Forms v době návrhu](developing-windows-forms-controls-at-design-time.md)
- [Chybové zprávy Návrháře formulářů Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))
