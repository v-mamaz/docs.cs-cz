### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>Změna v cestě oddělovací znak ve vlastnosti FullName položky ZipArchiveEntry objektů

|   |   |
|---|---|
|Podrobnosti|Pro aplikace, které cílí na rozhraní .NET Framework 4.6.1 a novější verze, cesta oddělovací znak změnil ze zpětné lomítko (&quot;&quot;) na dopředné lomítko (&quot;/&quot;) v <xref:System.IO.Compression.ZipArchiveEntry.FullName> vlastnost <xref:System.IO.Compression.ZipArchiveEntry> objekty vytvořené přetíženími <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> metoda. Tato změna přináší implementace rozhraní .NET do souladu s části 4.4.17.1 [. Specifikace formátu souboru ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) a umožňuje. ZIP archivy k dekomprimaci na jiné operační systémy. Dekompresi soubor zip vytvořené aplikace s cílem předchozí verzi rozhraní .NET Framework na jiný systém než Windows operační systémy, třeba Macintosh nepodaří zachovat strukturu adresáře. Například na Macintosh, vytvoří sadu souborů, jejichž název souboru zřetězí cesta k adresáři, společně s žádné zpětné lomítko (&quot;&quot;) znaků a název souboru. V důsledku toho není zachován struktura adresářů dekomprimovaných souborů.|
|Návrh|Dopad na tuto změnu. Soubory ZIP, které jsou dekomprimovat operačního systému Windows pomocí rozhraní API v rozhraní .NET Framework <xref:System.IO?displayProperty=nameWithType> oboru názvů musí být minimální, protože tato rozhraní API může bezproblémově zpracovat buď lomítko (&quot;/&quot;) ani zpětné lomítko (&quot; \&potřebná;) jako cesta oddělovací znak. Pokud se tato změna není žádoucí, se můžete rozhodnout mimo ho přidáním nastavení konfigurace, pro které [ \<runtime >](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) oddíl konfiguračního souboru aplikace. Následující příklad ukazuje, jak `<runtime>` části a `Switch.System.IO.Compression.ZipFile.UseBackslash` výslovný nesouhlas s přepínači:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Kromě toho aplikace, které cílí na předchozích verzích rozhraní .NET Framework, ale běží v rozhraní .NET Framework 4.6.1 a novějším můžete vyjádřit výslovný souhlas toto chování přidáním nastavení konfigurace, pro které [ \<runtime >](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) oddíl konfiguračního souboru aplikace. Následující příklad zobrazuje i `<runtime>` části a `Switch.System.IO.Compression.ZipFile.UseBackslash` přepínač výslovný souhlas.<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Rozsah|Edge|
|Version|4.6.1|
|Typ|Změna orientace|
|Ovlivněné rozhraní API|<ul><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType></li></ul>|
