---
title: Upřesnění zpracování inkoustu
ms.date: 03/30/2017
f1_keywords:
- AutoGeneratedOrientationPage
helpviewer_keywords:
- System.Windows.Input.StylusPlugIns classes
- InkCanvas control [WPF]
- ink [WPF], advanced handling
ms.assetid: abc8481a-f983-416f-b051-9168ac8b2ba3
ms.openlocfilehash: 840ab08faebe760a38ef344fd1c41818a838250b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367868"
---
# <a name="advanced-ink-handling"></a>Upřesnění zpracování inkoustu
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Se dodává s <xref:System.Windows.Controls.InkCanvas>, a je prvek vložíte do vaší aplikace k okamžitému spuštění shromažďování a zobrazování rukopisu. Nicméně pokud <xref:System.Windows.Controls.InkCanvas> ovládací prvek neposkytuje dost jemné úrovni ovládacího prvku, abyste mohli pro ovládací prvek na vyšší úrovni přizpůsobením vlastní kolekce inkoustů a tříd vykreslení inkoustu pomocí <xref:System.Windows.Input.StylusPlugIns>.  
  
 <xref:System.Windows.Input.StylusPlugIns> Třídy poskytují mechanismus pro implementaci nízké úrovně řízení nad <xref:System.Windows.Input.Stylus> vstup a dynamicky vykreslení inkoustu. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> Třída poskytuje mechanismus pro implementaci vlastního chování a použít na datový proud množství dat přicházejících z stylus zařízení k zajištění optimálního výkonu. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, Specializovaný <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>, umožňuje vám umožní přizpůsobit dynamicky datech pro vykreslení inkoustu v reálném čase, to znamená, že <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> vykreslí rukopis okamžitě, protože <xref:System.Windows.Input.StylusPoint> vygenerována data, aby se zobrazovalo "tok" z pera zařízení.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Rukopis s vlastním vykreslováním](custom-rendering-ink.md)  
  [Přijetí vstupu z pera](intercepting-input-from-the-stylus.md)  
  [Vytvoření ovládacího prvku vstupu rukopisu](creating-an-ink-input-control.md)  
  [Model vláken rukopisu](the-ink-threading-model.md)
