---
title: Obálky COM
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce15e0535bbd6bc67054c651a518f11cf9dd2ae1
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410352"
---
# <a name="com-wrappers"></a>Obálky COM
COM se liší od objektový model rozhraní .NET Framework důležité několika způsoby:  
  
-   Klienti objektů COM musí spravovat dobu života těchto objektů; modul common language runtime spravuje životnosti objektů ve svém prostředí.  
  
-   Klienti modelu COM objekty zjistit, zda je služba k dispozici vyžádáním rozhraní, které poskytuje služby a získat zpět ukazatel rozhraní, nebo ne. Klienti objektů .NET můžete získat popis objektu funkcí pomocí reflexe.  
  
-   NET objekty jsou umístěny v paměti spravuje prostředí pro spouštění rozhraní .NET Framework. Spouštěcí prostředí můžete přesouvat objekty v paměti kvůli výkonu a aktualizovat všechny odkazy na objekty, které přesunu. Nespravovaní klienti, které získaly ukazatel na objekt, spoléhají na objekt, který má zůstat ve stejném umístění. Tito klienti mají žádný mechanismus pro práci s objektem, jehož umístění nebyly odstraněny.  
  
 Chcete-li vyřešit tyto rozdíly, modul runtime poskytuje obálkové třídy, aby klienti spravovaných i nespravovaných myslíte, že volání objektů v rámci svých odpovídajících prostředí. Pokaždé, když spravovaného klienta volá metodu na objekt modelu COM, modul runtime vytvoří [obálka volatelná za běhu](runtime-callable-wrapper.md) (RCW). RCW abstraktní rozdíly mezi spravovanými a nespravovanými odkaz mechanismy mimo jiné. Modul runtime vytvoří také [obálka volatelná aplikacemi COM](com-callable-wrapper.md) (CCW) vrátit procesu a umožnit tak klient modelu COM bez problémů volat metodu na objekt .NET. Jak ukazuje následující obrázek, určuje, které obálkovou třídu modul runtime vytvoří perspektivy volající kód.  
  
 ![Přehled obálky COM](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 Ve většině případů poskytuje standardní obálky RCW nebo objekt CCW vygenerované modulem runtime odpovídající zařazování pro volání, které překračují hranice mezi modelem COM a rozhraní .NET Framework. Pomocí vlastních atributů, můžete volitelně můžete upravit způsob, jakým modul runtime představuje spravovaným a nespravovaným kódem.  
  
## <a name="see-also"></a>Viz také:
- [Rozšířená interoperabilita modelu COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Obálka volatelná za běhu](runtime-callable-wrapper.md)
- [Obálka volatelná aplikacemi COM](com-callable-wrapper.md)
- [Přizpůsobení standardních obálek](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))
- [Postupy: Přizpůsobení obálek Volatelných za běhu](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))
