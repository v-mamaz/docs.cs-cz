---
title: Data architektury služby
ms.date: 03/30/2017
ms.assetid: 2a2c8ddc-4e82-4e7f-a79f-97085c469517
ms.openlocfilehash: 5c65e9d473b5fe3f2b1c29824dcc1151abb0c3f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474013"
---
# <a name="service-framework-data"></a>Data architektury služby
Toto téma uvádí všechny výjimky generované Data architektury služby.  
  
## <a name="exception-list"></a>Seznam výjimek  
  
|Kód prostředku|Řetězec prostředku|  
|-------------------|---------------------|  
|AddressingExtensionInBadNS|Zadaný element v určeném oboru názvů není platný. To znamená, že zadaný element je duplicitní nebo že není právní rozšíření protože elementy rozšíření nemůže být v oboru názvů adresování.|  
|BinaryEncoderSessionInvalid|Binární kodér relace není platný, protože došlo k chybě dekódování předchozí zpráva.|  
|CannotDetectAddressingVersion|Nelze rozpoznat WS-Addressing verze. EndpointAddress nezačíná elementu.|  
|CouldNotFindNamespaceForPrefix|Zadaná předpona má žádná vazba oboru názvů v daném oboru.|  
|EncoderBadContentType|Nelze zpracovat k contentType.|  
|EncoderEnvelopeVersionMismatch|Verze obálky zadané příchozí zprávy neodpovídá zadané kodér. Ujistěte se, že je vazba konfigurována se stejnou verzí jako očekávané zprávy.|  
|EncoderMessageVersionMismatch|Verze zprávy zadaný odchozí zprávy neodpovídá zadané kodér. Ujistěte se, že se stejnou verzí jako zprávu, která je nakonfigurovaná vazby.|  
|ExtraContentIsPresentInFaultDetail|Další obsah Extensible Markup Language se nachází v elementu. Podrobnosti o selhání. Je povolen pouze jeden element.|  
|FilterBadTableType|Třída IMessageFilterTable vytvořená pro filtr nemůže být třídou MessageFilterTable nebo odvozené od třídy MessageFilterTable.|  
|FilterTableInvalidForLookup|Stav MessageFilterTable je poškozený. Nelze provést požadovanou vyhledávání.|  
|MandatoryHeaderNotUnderstood|Jedna nebo více povinných, že nebyly rozumí jednoduchého objektu přístup protokolu záhlaví bloky.|  
|MessageBodyIsStream|Text zprávy je datový proud.|  
|MessageBodyIsUnknown|Formát text zprávy neznámý.|  
|MessageBodyReaderInvalidReadState|Nejde je využívat zadané třídě ReadState čtečky textu zprávy.|  
|MessageTextEncodingNotSupported|Kódování zadaný text, který se používá ve formátu textu zprávy není podporována.|  
|MissingMessageID|Požadavku že zpráva chybí záhlaví MessageID. Záhlaví MessageID se vyžaduje ke korelaci odpovědi.|  
|MultipleMessageHeaders|Více než jeden hlavičku se zadaným názvem a oborem názvů nebyly nalezeny.|  
|MultipleMessageHeadersWithActor|Více než jeden hlavička se zadaným názvem, obor názvů a role nebyly nalezeny.|  
|MultipleRelatesToHeaders|Více než jeden související s hlavička s Zadaný vztah nebyly nalezeny. Pro každou relaci je povolený jenom jeden.|  
|QueryFunctionTypeNotSupported|Zadaný návratový typ IXsltContextFunction není podporován.|  
|QueryIteratorOutOfScope|Platnost XPathNodeIterator byla zrušena. Třídy XPathNodeIterators, které se předávají jako argumenty IXsltContextFunctions platí pouze v rámci funkce. Nemůže být uložená v mezipaměti pro pozdější použití nebo vráceným funkcí.|  
|QueryVariableNull|Metody IXsltContextVariable nemůže vrátit hodnotu null.|  
|QueryVariableTypeNotSupported|Zadaný IXsltContextVariable odvozený typ není podporován.|  
|ReceiveShutdownReturnedMessage|Kanál přijal neočekávanou zprávu vstupní spolu s určenou akcí při zavírání. Zavřete kanál, pokud neočekáváte další zprávy o zadávání.|  
|XmlBufferInInvalidState|Došlo k vnitřní chybě. Operaci nelze provést z důvodu stavu XML vyrovnávací paměti.|  
|XmlBufferQuotaExceeded|Potřeba ukládat do vyrovnávací paměti obsah Extensible Markup Language velikost překročila kvótu pro vyrovnávací paměti.|
