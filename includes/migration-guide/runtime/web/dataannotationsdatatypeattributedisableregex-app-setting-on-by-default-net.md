### <a name="dataannotationsdatatypeattributedisableregex-app-setting-is-on-by-default-in-net-framework-472"></a><span data-ttu-id="3966a-101">nastavení aplikace "dataAnnotations:dataTypeAttribute:disableRegEx" je ve výchozím v rozhraní .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="3966a-101">"dataAnnotations:dataTypeAttribute:disableRegEx" app setting is on by default in .NET Framework 4.7.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3966a-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="3966a-102">Details</span></span>|<span data-ttu-id="3966a-103">V rozhraní .NET Framework 4.6.1, nastavení aplikace (<code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code>) byla zavedená umožňuje uživatelům zakázat používání regulárních výrazů v atributy datového typu (například <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>, <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType>, a <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="3966a-103">In .NET Framework 4.6.1, an app setting (<code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code>) was introduced that allows users to disable the use of regular expressions in data type attributes (such as <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>, <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType>, and <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="3966a-104">To pomáhá snížit ohrožení zabezpečení, jako je například zabraňující možnost útoku Denial of Service pomocí konkrétní regulárních výrazů.</span><span class="sxs-lookup"><span data-stu-id="3966a-104">This helps to reduce security vulnerability such as avoiding the possibility of a Denial of Service attack using specific regular expressions.</span></span><br/><span data-ttu-id="3966a-105">V rozhraní .NET Framework 4.6.1, toto nastavení aplikace zakázat RegEx využití byla nastavena na <code>false</code> ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="3966a-105">In .NET Framework 4.6.1, this app setting to disable RegEx usage was set to <code>false</code> by default.</span></span> <span data-ttu-id="3966a-106">Rovnou začít tématem rozhraní .NET Framework 4.7.2, tato konfigurace přepínač je nastaven na hodnotu <code>true</code> ve výchozím nastavení k dalšímu snížení zabezpečení ohrožení zabezpečení pro webové aplikace, které cílí na rozhraní .NET Framework 4.7.2 a vyšší.</span><span class="sxs-lookup"><span data-stu-id="3966a-106">Staring with .NET Framework 4.7.2, this config switch is set to <code>true</code> by default to further reduce secure vulnerability for web applications that target .NET Framework 4.7.2 and above.</span></span>|
|<span data-ttu-id="3966a-107">Návrh</span><span class="sxs-lookup"><span data-stu-id="3966a-107">Suggestion</span></span>|<span data-ttu-id="3966a-108">Pokud zjistíte, že regulární výrazy ve webové aplikaci po upgradu na rozhraní .NET Framework 4.7.2 nebudou fungovat, můžete je aktualizovat hodnotu <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> nastavení <code>false</code> se vrátit k předchozí chování.</span><span class="sxs-lookup"><span data-stu-id="3966a-108">If you find that regular expressions in your web application do not work after upgrading to .NET Framework 4.7.2, you can update the value of the <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> setting to <code>false</code> to revert to the previous behavior.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appsettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot; value=&quot;false&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appsettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="3966a-109">Rozsah</span><span class="sxs-lookup"><span data-stu-id="3966a-109">Scope</span></span>|<span data-ttu-id="3966a-110">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="3966a-110">Minor</span></span>|
|<span data-ttu-id="3966a-111">Version</span><span class="sxs-lookup"><span data-stu-id="3966a-111">Version</span></span>|<span data-ttu-id="3966a-112">4.7.2</span><span class="sxs-lookup"><span data-stu-id="3966a-112">4.7.2</span></span>|
|<span data-ttu-id="3966a-113">Typ</span><span class="sxs-lookup"><span data-stu-id="3966a-113">Type</span></span>|<span data-ttu-id="3966a-114">Modul runtime</span><span class="sxs-lookup"><span data-stu-id="3966a-114">Runtime</span></span>|
