---
title: Přehled technologie oblastí
ms.date: 03/30/2017
helpviewer_keywords:
- window regions [WPF]
- Win32 code [WPF], WPF interoperation
- Win32 code [WPF], airspace
- airspace [WPF]
- interoperability [WPF], airspace
- Win32 code [WPF], window regions
ms.assetid: b7cc350f-b9e2-48b1-be14-60f3d853222e
ms.openlocfilehash: 3fc325f1b4bb4eca73e051732810c9d9853ff4d7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352483"
---
# <a name="technology-regions-overview"></a>Přehled technologie oblastí
Pokud více technologií prezentace se používají v aplikaci, například WPF, Win32 či DirectX, sdílejí musí vykreslování oblastí v rámci běžných okno nejvyšší úrovně. Toto téma popisuje problémy, které by mohly ovlivnit prezentace a vstup pro součinnost aplikaci WPF.  
  
## <a name="regions"></a>Oblasti  
 V rámci okno nejvyšší úrovně pohodlným, který má každý HWND, který se skládá z technologií součinnost aplikace svou vlastní oblasti (také nazývané "vzdušného prostoru"). Každý pixel v okně patří přesně jeden HWND, který představuje oblasti tohoto HWND. (Přesněji řečeno, je více než jeden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oblast, pokud existuje více než jeden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND, ale pro účely této diskuse, můžete předpokládat, je jen jeden). Oblast znamená, že všechny vrstvy nebo ostatní okna, které budou pokoušet o vykreslování nad tento bod během životního cyklu aplikace musí být součástí stejné technologie vykreslení úrovni. Při vykreslování [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pixelů přes [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] vede k nežádoucím výsledky a je zakázáno co nejvíc prostřednictvím vzájemná spolupráce grafického subsystému [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].  
  
### <a name="region-examples"></a>Příklady oblasti  
 Následující obrázek znázorňuje aplikaci, která kombinuje [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Jednotlivé technologie používá svůj vlastní samostatný, které se nepřekrývají sadu pixelů a nedochází k potížím oblasti.  
  
 ![Okno, které nemá žádné problémy s vzdušného prostoru](./media/migrationinteroparchitectarticle01.png "MigrationInteropArchitectArticle01")  
  
 Předpokládejme, že tato aplikace používá pozice ukazatele myši na vytvořit animaci, která se pokusí o vykreslování pomocí kteréhokoli z těchto tří oblastí. Bez ohledu na technologii, která je zodpovědná za samotný animace těmito technologiemi, by mohla narušit oblasti Další dvě. Následující obrázek znázorňuje pokusu o vykreslení kruh WPF přes oblast Win32.  
  
 ![Spolupráce diagram](./media/migrationinteroparchitectarticle02.png "MigrationInteropArchitectArticle02")  
  
 Jiné porušení je, pokud se pokusíte použít transparentnosti/alfa míchání mezi různými technologiemi.  Na následujícím obrázku [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pole je v rozporu [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] a [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] oblastech. Protože pixelů, který [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pole jsou poloprůhledného, bylo by nutné vlastnictvím obě [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], který není možné.  Takže to jiného narušení a nemůže být vytvořena.  
  
 ![Spolupráce diagram](./media/migrationinteroparchitectarticle03.png "MigrationInteropArchitectArticle03")  
  
 Předchozí tři příklady používá oblasti obdélníkový, ale je možné různých tvarů.  V oblasti můžete mít například díry. Je vidět na následujícím obrázku [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] oblasti s obdélníkové hole Toto je velikost [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] oblastech kombinovat.  
  
 ![Spolupráce diagram](./media/migrationinteroparchitectarticle04.png "MigrationInteropArchitectArticle04")  
  
 Oblasti lze také kompletně neobdélníkových nebo žádný obrazec describable podle [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] HRGN (oblast).  
  
 ![Spolupráce diagram](./media/migrationinteroparchitectarticle05.png "MigrationInteropArchitectArticle05")  
  
## <a name="transparency-and-top-level-windows"></a>Transparentnost a nejvyšší úrovně Windows  
 Správce oken ve Windows zpracovává jenom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] HWND. Proto se každý [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> je popisovačem HWND. <xref:System.Windows.Window> HWND musí dodržovat obecná pravidla pro všechny HWND. V rámci této HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kódu můžete dělat všechno, co celkové [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] podporovat. Ale pro interakce se další HWND na ploše [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] musí dodržovat [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] zpracováním a vykreslováním pravidla.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] podporuje neobdélníkových oken pomocí [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]– HRGNs neobdélníkových oken a vrstvami windows pro platformu alpha jednotlivých pixelů.  
  
 Konstantní alfa a barvu klíče nejsou podporovány.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Vrstvené okno funkce se liší podle platformy.  
  
 Vrstvené windows můžete provádět celé okno více průchody průsvitných (poloprůhlednosti) tak, že zadáte hodnotu alfa a platí pro každý pixel v okně.  ([!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ve skutečnosti alfa jednotlivých pixelů podporuje, ale to je velmi obtížné v praktických programů použít, protože v tomto režimu by je potřeba vykreslit všech podřízených HWND sami, včetně dialogových oken a rozevírací seznamy).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] podporuje HRGNs; Existují však není spravovaná [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] pro tuto funkci. Používáte platformu vyvolání a <xref:System.Windows.Interop.HwndSource> volat odpovídající [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. Další informace najdete v tématu [volání nativních funkcí ze spravovaného kódu](/cpp/dotnet/calling-native-functions-from-managed-code).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Vrstvené windows mají různé funkce v různých operačních systémech. Důvodem je, že [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] používá [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] k vykreslení, a vrstvami windows byly primárně určený pro [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] vykreslování, není [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] vykreslování.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hardware podporuje akcelerované vrstveným windows na [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)] a novější. Hardware accelerated vrstveným windows na [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)] vyžadují podporu – od [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)], takže funkce závisí na verzi [!INCLUDE[TLA#tla_dx](../../../../includes/tlasharptla-dx-md.md)] v daném počítači.  
  
-   [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nepodporuje transparentnosti barevné klíče, protože [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nemůže zaručit, že přesná barva jste požádali, zejména pokud vykreslování hardwarově urychlené vykreslování.  
  
-   Pokud vaše aplikace běží na [!INCLUDE[TLA2#tla_winxp](../../../../includes/tla2sharptla-winxp-md.md)], vrstvený windows nad [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] barvou přepínal povrchy při [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] vykresluje aplikace.  (Pořadí vykreslování skutečné je, že [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] potom skryje okno vrstvami [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] kreslení a potom [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] vrátí zpět vrstvami okno).  Jinou hodnotu než[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vrstvami windows také mít toto omezení.  
  
## <a name="see-also"></a>Viz také:
- [Vzájemná spolupráce grafického subsystému WPF a systému Win32](wpf-and-win32-interoperation.md)
- [Návod: Hostování hodin WPF v Win32](walkthrough-hosting-a-wpf-clock-in-win32.md)
- [Hostování obsahu Win32 v subsystému WPF](hosting-win32-content-in-wpf.md)
