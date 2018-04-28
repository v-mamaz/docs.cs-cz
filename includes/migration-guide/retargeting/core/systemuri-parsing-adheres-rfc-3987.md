### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>Analýza System.Uri dodržuje RFC 3987

|   |   |
|---|---|
|Podrobnosti|Analýza URI došlo ke změně v rozhraní .NET 4.5 několika způsoby. Upozorňujeme však, že tyto změny se projeví pouze kód cílení na rozhraní .NET 4.5. Binární cíle rozhraní .NET 4.0, původní chování budou zachována. Změny v identifikátoru URI analýza v rozhraní .NET 4.5 patří:<ul><li>Identifikátor URI analýza provede normalizaci a kontrola souladu s pravidly nejnovější IRI v dokumentu RFC 3987 znak.</li><li>Unicode normalizaci formuláře C se provádí pouze v části hostitele identifikátoru URI.</li><li>Neplatný mailto: identifikátory URI nyní způsobí výjimku.</li><li>Nyní se zachovají koncové tečky na konci tohoto segmentu cesty.</li><li><code>file://</code> Identifikátory URI není vyhnuli <code>?</code> znak.</li><li>Řídicí znaky Unicode <code>U+0080</code> prostřednictvím <code>U+009F</code> nejsou podporovány.</li><li>Znaky čárkami <code>,</code> nebo <code>%2c</code> nejsou automaticky neuvozené.</li></ul>|
|Návrh|Pokud původní analýzy sémantiky rozhraní .NET 4.0 URI jsou nutné (často nejsou), můžete použít pomocí cílení na rozhraní .NET 4.0. Můžete to provést pomocí <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> na sestavení, nebo prostřednictvím systému projektu sady Visual Studio uživatelského rozhraní na stránce 'projektu vlastnosti'.|
|Rozsah|Hlavní|
|Version|4.5|
|Typ|Změna orientace|
|Ovlivněné rozhraní API|<ul><li><xref:System.Uri.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.UriKind)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.Uri,System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li></ul>|
