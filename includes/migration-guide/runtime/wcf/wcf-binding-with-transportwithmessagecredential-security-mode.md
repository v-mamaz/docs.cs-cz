### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>Vazby WCF s režim zabezpečení TransportWithMessageCredential

|   |   |
|---|---|
|Podrobnosti|Od verze rozhraní .NET Framework 4.6.1, vazby WCF, který používá režim zabezpečení TransportWithMessageCredential lze přijímat zprávy s nepodepsané &quot;k&quot; hlavičky pro zabezpečení asymetrické klíče. Ve výchozím nastavení, nepodepsané &quot;k&quot; bude pokračovat hlaviček zamítnutí v rozhraní .NET 4.6.1. Jsou pouze přijaty pokud aplikace požádá do tento nový režim operace pomocí Switch.System.ServiceModel.AllowUnsignedToHeader konfigurace přepínače. Protože se jedná o funkci přihlášení, by neměly ovlivnit chování existující aplikace.|
|Návrh|Protože se jedná o funkci přihlášení, by neměly ovlivnit chování existující aplikace. Chcete-li určit, zda se má použít nové chování, nebo Ne, použijte následující nastavení konfigurace:<pre><code>&lt;runtime&gt;<br />&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.AllowUnsignedToHeader=true&quot; /&gt;<br />&lt;/runtime&gt;</code></pre>|
|Rozsah|Transparentní|
|Version|4.6.1|
|Typ|Modul runtime|
|Ovlivněné rozhraní API|<ul><li><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li></ul>|
