### <a name="deadlock-may-result-when-using-reentrant-services"></a>Zablokování může dojít při použití vícenásobné služeb

|   |   |
|---|---|
|Podrobnosti|Vícenásobné služby, který omezuje instance služby na jedno vlákno provádění v čase může vést k zablokování. Služby, které jsou náchylné k tomuto problému dojde, bude mít následující <xref:System.ServiceModel.ServiceBehaviorAttribute> ve svém kódu:<pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]&#13;&#10;</code></pre>|
|Doporučení|A tento problém vyřešit, můžete provést následující:<ul><li>Nastavte režim souběžnosti služby <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> nebo &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;. Příklad:</li></ul><pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single)]&#13;&#10;</code></pre><ul><li>Nainstalujte nejnovější aktualizaci rozhraní .NET Framework 4.6.2, nebo upgradujte na novější verzi rozhraní .NET Framework. Zakáže tok <xref:System.Threading.ExecutionContext> v <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Toto chování je možné konfigurovat; je ekvivalentní k přidání nastavení aplikace, které následující konfigurační soubor:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Hodnota <code>Switch.System.ServiceModel.DisableOperationContextAsyncFlow</code> nikdy musí být nastavená na <code>false</code> Rentrant služeb.|
|Rozsah|Vedlejší|
|Version|4.6.2|
|Typ|Změna cílení|
|Ovlivněná rozhraní API|<ul><li><xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType></li></ul>|

