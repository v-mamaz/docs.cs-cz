### <a name="accessibility-improvements-in-windows-workflow-foundation-wf-workflow-designer"></a>Vylepšení přístupnosti v Návrháři pracovních postupů Windows Workflow Foundation (WF)

|   |   |
|---|---|
|Podrobnosti|Jak funguje s technologie usnadnění zlepšují návrháře pracovních postupů Windows Workflow Foundation (WF). Tato vylepšení zahrnují následující změny:<ul><li>Pořadí karet se změní na zleva doprava a shora dolů v některé ovládací prvky:</li><li>Okno inicializovat korelace pro nastavení korelace dat pro <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity</li><li>Okno obsahu definice pro <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity</li><li>Další funkce jsou dostupné prostřednictvím klávesnice:</li><li>Při úpravě vlastností aktivity, vlastnost skupiny lze sbalit pomocí klávesnice poprvé, které se zaměřuje.</li><li>Ikony upozornění jsou nyní k dispozici pomocí klávesnice.</li><li>Tlačítko více vlastností v okně Vlastnosti je nyní přístupné klávesnice.</li><li>Klávesnice uživatelé teď můžou používat položky hlavičky v podoknech argumenty a proměnné Návrháře pracovního postupu.</li><li>Lepší viditelnost položek s fokusem, jako např. kdy:</li><li>Přidání řádků do datových mřížek používají návrháři návrháře pracovních postupů a aktivit.</li><li>Stisknutím klávesy tabulátor procházíte polí v <xref:System.ServiceModel.Activities.ReceiveReply> a <xref:System.ServiceModel.Activities.SendReply> aktivity.</li><li>Nastavení výchozí hodnoty pro proměnné nebo argumenty</li><li>Nyní můžete správné rozpoznání čtečky obrazovky:</li><li>Nastavte zarážky v Návrháři pracovních postupů.</li><li><xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, A <xref:System.ServiceModel.Activities.CorrelationScope> aktivity.</li><li>Obsah <xref:System.ServiceModel.Activities.Receive> aktivity.</li><li>Cílový typ <xref:System.Activities.Statements.InvokeMethod> aktivity.</li><li>ComboBox – výjimka a nakonec v části <xref:System.Activities.Statements.TryCatch> aktivity.</li><li>ComboBox – typ zprávy, rozdělovače v okně Přidat inicializátory korelace, obsahu definice okno a okno CorrelatesOn definice v zasílání zpráv aktivity (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply>).</li><li>Stav počítač přejde a přejde cíle.</li><li>Poznámky a konektory na <xref:System.Activities.Statements.FlowDecision> aktivity.</li><li>Kontextové (klikněte pravým tlačítkem) nabídky pro aktivity.</li><li>Editory hodnotu vlastnosti, na tlačítko Vymazat vyhledat, podle kategorie a abecedním řazení tlačítek a dialogové okno Editor výraz ve vlastnosti mřížky.</li><li>Procento přiblížení v Návrháři pracovních postupů.</li><li>Oddělovač v <xref:System.Activities.Statements.Parallel> a <xref:System.Activities.Statements.Pick> aktivity.</li><li><xref:System.Activities.Statements.InvokeDelegate> Aktivity.</li><li>Vyberte typy okna pro slovník aktivity (<code>Microsoft.Activities.AddToDictionary&lt;TKey,TValue&gt;</code>, <code>Microsoft.Activities.RemoveFromDictionary&lt;TKey,TValue&gt;</code>atd.).</li><li>Okno Procházet a vyberte typ formátu .NET.</li><li>Popis cesty v Návrháři pracovních postupů.</li><li>Uživatelé, kteří se rozhodnou, vysoký kontrast motivy uvidí řady vylepšení v viditelnost návrháře pracovních postupů a jeho ovládací prvky, jako jsou lépe protějšek poměr mezi elementy a použít pro prvky výběru výraznější výběr polí.</li></ul>|
|Návrh|Pokud máte aplikace pomocí návrháře znovu hostovaných pracovních postupů, vaše aplikace mohou těžit z výhod tyto změny pomocí některé z těchto akcí:<ul><li>Znovu zkompiluje aplikace cílí na rozhraní .NET Framework 4.7.1. Tyto změny usnadnění jsou povolené ve výchozím nastavení.</li><li>Pokud aplikace cílí rozhraní .NET Framework 4.7 nebo starší, ale běží na rozhraní .NET Framework 4.7.1, můžete zamítnutí tyto starší verze usnadnění chování přidáním následující [AppContext přepínač](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) k <code>&lt;runtime&gt;</code> části z souboru app.config souborů a nastavte ji na <code>false</code>, jak ukazuje následující příklad.</li></ul><pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Aplikace, které cílí na rozhraní .NET Framework 4.7.1 nebo novější a chcete zachovat starší verze usnadnění chování můžete vyjádřit výslovný souhlas s použitím funkce usnadnění starší verze explicitně nastavením tento přepínač AppContext na <code>true</code>.|
|Rozsah|Vedlejší|
|Version|4.7.1|
|Typ|Změna orientace|
