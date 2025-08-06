---
lab:
  title: '1.2: Hinzufügen von benutzerdefiniertem Wissen'
---

# Hinzufügen von benutzerdefiniertem Wissen

In dieser Übung aktualisieren Sie den deklarativen Agent, den Sie in der vorherigen Übung erstellt haben, mit benutzerdefinierten Anweisungen und Groundingdaten. Diese Übung setzt voraus, dass Sie über eine SharePoint-Website mit einer Dokumentbibliothek namens „Produkte“ verfügen, die Beispielproduktdateien enthält.

Diese Übung dauert ca. **20** Minuten.

## Vor der Installation

Bevor Sie diese Übung starten können, müssen Sie die produktbezogenen Dokumente in Microsoft 365 hochladen, die der deklarative Agent als Grounding-Daten verwendet. Führen Sie die folgenden Schritte aus, um sich auf die Übung vorzubereiten.

> [!NOTE]
> Wenn Sie Dokumente auf eine neue SharePoint Online-Website hochladen, gibt es eine Verzögerung, bis die Dokumente indiziert sind und von Copilot verwendet werden können. Wenn Sie Ihren Agent sofort testen möchten, laden Sie die Dokumente auf eine **vorhandene** Website hoch. Die Dokumente werden indiziert und stehen dem Agent unverzüglich zur Verfügung. Wenn Sie eine neue SharePoint Online-Website verwenden, kann es länger dauern, bis die Dokumente indiziert und für Copilot verfügbar sind.
>
> **Die nachstehenden Anweisungen führen Sie durch das Hochladen der Dokumente auf eine neue Website**. Wenn Sie eine bereits vorhandene Website verwenden möchten, beginnen Sie mit dem Abschnitt mit der Bezeichnung **Beispieldaten hochladen** und verwenden Sie Ihre vorhandene Bibliothek anstelle der Bibliothek **Produkte**.

### Herunterladen der Beispieldaten

1. Navigieren Sie in einem Webbrowser zum [GitHub-Repository](https://github.com/MicrosoftLearning/MS-4022-Extend-Microsoft-365-Copilot-in-Copilot-Studio/blob/master/Allfiles/Products.zip) des Kurses.
1. Klicken Sie auf die Schaltfläche **Rohdatei herunterladen**, um die Datei **Products.zip** herunterzuladen.

    :::image type="content" source="../media/download-github.png" alt-text="Screenshot von Microsoft Edge mit hervorgehobener Schaltfläche zum Herunterladen der Rohdatendatei in GitHub.":::

1. **Öffnen Sie** den heruntergeladenen Ordner, und **extrahieren Sie alle** Inhalte in einen neuen Ordner auf Ihrem Computer namens `Products`, auf den Sie später zugreifen können.

### Erstellen Sie eine SharePoint-Site

1. Navigieren Sie in einem Webbrowser zu [https://www.microsoft365.com](https://www.microsoft365.com) und **melden Sie sich** mit dem Microsoft 365-Konto an, das Sie für dieses Lab verwenden.
1. Wählen Sie im linken Menü **Apps** (Gitter-Symbol) und dann **SharePoint** aus dem Katalog der Apps.
1. Wählen Sie im linken Menü **Erstellen** (Plus-Symbol) und dann **Site**.
1. Wählen Sie **Teamwebsite** als Art der Site.
1. Auf der Seite **Vorlage auswählen**, wählen Sie **Standardteam**.
1. Auf der Seite **Vorschau** wählen Sie **Vorlage verwenden**.
1. Auf der Seite **Benennen Sie Ihre Website** geben Sie `Product support` ein und wählen **Weiter**.
1. Auf der nächsten Konfigurationsseite ändern Sie die **Datenschutzeinstellungen** in **Öffentlich**.
1. Wählen Sie **Standort anlegen**. Die Erstellung der Website kann einige Augenblicke dauern, bevor die Schaltfläche **Fertig stellen** aktiviert wird.
1. Wählen Sie **Fertig stellen** aus.

### Erstellen einer Dokumentbibliothek

1. Wählen Sie auf der SharePoint-Website **Produktsupport** die Schaltfläche **Neu** oben auf der Seite und wählen Sie dann **Dokumentenbibliothek**.
1. Wählen Sie auf der Seite **Eine neue Dokumentenbibliothek erstellen** die Option **Leere Bibliothek**.
1. Geben Sie in das Feld **Name** `Products` ein und wählen Sie **Erstellen**.

### Hochladen von Beispieldaten

1. Wählen Sie in der Bibliothek **Produkte** die Schaltfläche **Hochladen** und wählen Sie dann **Dateien**.
1. Navigieren Sie zu dem Ordner auf Ihrem Computer, in dem Sie die Beispieldateien in einem früheren Schritt gespeichert haben.
1. **Markieren Sie alle** Dateien in Ihrem lokalen Ordner Produkte und wählen Sie dann **Öffnen**, um sie auf SharePoint hochzuladen.
1. Warten Sie, bis der Upload abgeschlossen ist. Die Dateien werden nun in der **Produktbibliothek** in SharePoint angezeigt.

### Kopieren der SharePoint-URL

Kopieren Sie anschließend die direkte URL der Website, die Sie bei der Konfiguration des Wissens Ihres Agents verwenden möchten.

1. Wählen Sie auf der Bibliotheksseite **Produkte** in SharePoint das Symbol **Einstellungen** oben rechts und wählen Sie **Bibliothekseinstellungen** und dann **Weitere Bibliothekseinstellungen**.

    :::image type="content" source="../media/sharepoint-library-settings.png" alt-text="Screenshot von Microsoft Edge, der die Option Bibliothekseinstellungen im Einstellungsmenü zeigt.":::

1. Suchen Sie die **Webadresseneigenschaft**. Ihre **SharePoint-Site-URL** ist der Teil der Webadresse, der das Format `https://DOMAIN.sharepoint.com/sites/SITE_NAME/LIBRARY_NAME` hat. Ihre URL sollte `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products` lauten.
1. **Kopieren Sie** Ihre SharePoint-Site-URL, und speichern Sie sie für die Verwendung in anstehenden Lab-Schritten.

## Konfigurieren Ihres Agents mit benutzerdefiniertem Wissen

Fügen Sie Ihrem Agent die SharePoint-URL als grundlegende Wissensquelle hinzu.

### Hinzufügen einer SharePoint-URL

1. Navigieren Sie in einem Webbrowser zu [Microsoft Copilot Studio](https://copilotstudio.microsoft.com/) unter `https://copilotstudio.microsoft.com`.
1. Wählen Sie **Agents** aus.
1. Wählen Sie **Copilot für Microsoft 365** aus.
1. Wählen Sie Ihren **Produktsupport**-Agent aus.
1. Wählen Sie im Abschnitt **Wissen** auf der Übersichtsseite des Agents die Option **Wissensdatenbank hinzufügen** aus.

    ![Screenshot von Copilot Studio in Microsoft Edge mit hervorgehobener Schaltfläche „Wissen hinzufügen“ für den Produkt-Support-Agent.](../Media/product-support-add-knowledge.png)

1. Wählen Sie auf der Seite **Wissen hinzufügen** des angezeigten Assistenten die Option **SharePoint** aus.
1. Fügen Sie in das Textfeld die URL Ihrer SharePoint-Bibliothek **Produkte** ein und wählen Sie dann **Hinzufügen**. Dies sollte im folgenden Format erfolgen: `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products`.

1. Wählen Sie im Fenster **SharePoint hinzufügen** die Option **Hinzufügen** und warten Sie, bis die Wissensquelle zum Agent hinzugefügt wurde. Dies kann ein oder zwei Minuten dauern.
1. Beachten Sie, dass die Bibliothek **Produkte** im Abschnitt **Wissen** der Übersichtsinformationen des Agents aufgeführt ist.

> **Hinweis**: Copilot Studio-Agents greifen im Namen der Benutzenden auf Dokumente zu. Ihr Agent kann nur Antworten und Inhalte von Dokumenten erhalten, auf die Ihre Endbenutzenden Zugriff haben.

### Aktualisieren von benutzerdefinierten Anweisungen

Aktualisieren Sie als Nächstes die Anweisungen des Agents, um zu beschreiben, wie der Agent die Wissensquelle verwenden soll.

1. Wählen Sie auf der Übersichtsseite des Agents in Copilot Studio im Abschnitt **Details** die Option **Bearbeiten** aus.
1. Aktualisieren Sie den Inhalt des Textfelds **Anweisungen** wie folgt: `You are an agent tasked with answering questions about Contoso Electronics products. Start every response by enthusiastically thanking the user for their question or comment, then respond to their question or comment. You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.`
1. Wählen Sie im Abschnitt **Details** die Option **Speichern** aus.

## Testen Ihres Agents in Copilot Studio

Testen Sie schließlich die Fähigkeit Ihres Agents, die benutzerdefinierte Wissensquelle zu verwenden.

1. Wählen Sie im Bereich**Agent testen** auf der Übersichtsseite Ihres Agents in Copilot Studio die Schaltfläche **Aktualisieren**, um den Testbereich zu aktualisieren und die neuesten Änderungen Ihres Agents zu laden.
1. Geben Sie im Textfeld für die Testkonversation `Tell me about Eagle Air` ein und senden Sie die Nachricht.
1. Warten Sie auf die Antwort. Beachten Sie, dass die Antwort Informationen über die Drohne Eagle Air enthält. Die Antwort enthält Zitate und Verweise auf das in SharePoint gespeicherte Eagle Air-Dokument.

Lassen Sie uns einige weitere Eingabeaufforderungen ausprobieren:

1. Geben Sie im Nachrichtenfeld `Recommend a product suitable for a farmer` ein und senden Sie die Nachricht.
1. Warten Sie auf die Antwort. Beachten Sie, dass die Antwort Informationen über Eagle Air und einige zusätzliche Hintergrundinformationen darüber enthält, warum Eagle Air empfohlen wird. Die Antwort enthält Zitate und Verweise auf das in OneDrive gespeicherte Eagle Air-Dokument.
1. Geben Sie im Nachrichtenfeld `Explain why the Eagle Air is more suitable than Contoso Quad` ein und senden Sie die Nachricht.
1. Warten Sie auf die Antwort. Beachten Sie, dass die Antwort ausführlicher erklärt, warum die Eagle Air für den Einsatz durch Landwirte besser geeignet ist als die Contoso Quad.

Abschließend testen wir die Fallbackantwort, indem wir eine Frage stellen, die der Agent nicht beantworten kann:

1. Geben Sie im Nachrichtenfeld `When was Mark8 released?` ein und senden Sie die Nachricht.
1. Warten Sie auf die Antwort. Beachten Sie, dass die Antwort darauf hinweist, dass der Agent sich an das Team wenden sollte, das für weitere Unterstützung gemäß den Anweisungen zuständig ist.
