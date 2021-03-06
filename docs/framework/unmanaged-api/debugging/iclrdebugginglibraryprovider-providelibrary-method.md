---
title: ICLRDebuggingLibraryProvider::ProvideLibrary – metoda
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd1038fdc8b22b99e1c8c7b753b46b9ce877355
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496440"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>ICLRDebuggingLibraryProvider::ProvideLibrary – metoda
Získá zprostředkovatele knihovny, rozhraní zpětného volání, které umožňuje knihovnám ladění specifickým pro verzi modulu runtime (CLR) k vyhledání a načtení na požádání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a>Parametry  
 `pwszFilename`  
 [in] Název modulu žádá.  
  
 `dwTimestamp`  
 [in] Časové razítko uložené v hlavičce souboru COFF soubory PE.  
  
 `pLibraryProvider`  
 [in] `SizeOfImage` Pole uloženo v hlavičce souboru COFF volitelný soubor PE souborů.  
  
 `hModule`  
 [out] Popisovač na požadovaný modul.  
  
## <a name="return-value"></a>Návratová hodnota  
 Tato metoda vrátí následující konkrétní HRESULT, stejně jako hodnota HRESULT chyby, které označují selhání metoda.  
  
|HRESULT|Popis|  
|-------------|-----------------|  
|S_OK|Metoda byla úspěšně dokončena.|  
  
## <a name="exceptions"></a>Výjimky  
  
## <a name="remarks"></a>Poznámky  
 `ProvideLibrary` Umožňuje ladicí program poskytuje moduly, které jsou potřeba pro ladění konkrétní soubory CLR, jako je například knihovna mscordbi.dll a souboru mscordacwks.dll. Obslužné rutiny modulu musí zůstat platný až do volání [iclrdebugging::canunloadnow –](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) metoda naznačuje, že může být uvolněna, v tomto okamžiku je odpovědností volajícího uvolnit úchyty.  
  
 Ladicí program může použít všechny dostupné prostředky vyhledejte nebo pořídit modulu ladění.  
  
> [!IMPORTANT]
>  Tato funkce umožňuje rozhraní API volajícímu zadat moduly, které obsahují spustitelný soubor a potenciálně škodlivý kód. Jako bezpečnostní opatření, nepoužívejte, volající `ProvideLibrary` distribuovat veškerý kód, že není natolik, abyste spuštění samotný.  
>   
>  Pokud je zjištěno závažný bezpečnostní problém již vydané knihovny, jako je například knihovna mscordbi.dll nebo souboru mscordacwks.dll, nejde opravit shimu rozpoznat chybná verze souborů. Překrytí pak můžete vydávat žádosti pro nainstalovanou verzí souborů a odmítnout chybná verze, pokud nejsou zadány žádné požadavku. Tato situace může nastat, pouze v případě, že uživatel má použít pro novou verzi shimu. Verze bez opravy zabezpečení se nadále zranitelné.  
  
## <a name="requirements"></a>Požadavky  
 **Platformy:** Zobrazit [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Záhlaví:** CorDebug.idl, CorDebug.h  
  
 **Knihovna:** CorGuids.lib  
  
 **Verze rozhraní .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Viz také:
- [Rozhraní pro ladění](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Ladění](../../../../docs/framework/unmanaged-api/debugging/index.md)
