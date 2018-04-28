### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng nyní správně načte klíče RSA nestandardní velikost klíče

|   |   |
|---|---|
|Podrobnosti|V rozhraní .NET Framework verze starší než 4.6.2, jsou zákazníkům nestandardní velikosti klíče pro certifikáty RSA nelze získat přístup přes tyto klíče <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> a <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> rozšiřující metody.  A <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> se zprávou &quot;nepodporuje požadovanou velikost klíče&quot; je vyvolána výjimka. V rozhraní .NET Framework 4.6.2 Tento problém byl opraven. Podobně <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> a <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> teď spolupracovat s nestandardní velikosti klíče bez způsobení <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>s.|
|Návrh|Pokud je zpracování logiky, která závisí na předchozí chování všech výjimek kde <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> se vyvolá, když se používají nestandardní velikosti klíče, zvažte odebrání logiku.|
|Rozsah|Edge|
|Version|4.6.2|
|Typ|Změna orientace|
|Ovlivněné rozhraní API|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|
