---
lab:
  title: '2.1: Erstellen einer Promptaktion'
---

# Erstellen einer Promptaktion

In dieser Übung erstellen Sie eine Promptaktion, testen den Prompt in Copilot Studio und testen den Prompt in einem Copilot Agent. Sie erstellen eine Promptaktion, die den Benutzenden hilft, ihre bloßen Ideen in organisierte Marketingvorschläge zu verwandeln, die einem bestimmten Format und Richtlinien folgen.

Diese Übung dauert ca. **15** Minuten.

## Erstellen einer benutzerdefinierten Eingabeaufforderung in Copilot Studio

1. Öffnen Sie Copilot Studio in Ihrem Webbrowser, indem Sie zu [Copilot Studio](https://copilotstudio.microsoft.com) navigieren unter `https://copilotstudio.microsoft.com`.
1. Wählen Sie im linken Navigationsbereich **Tools** aus.
1. Wählen Sie **Neu erstellen** und anschließend **Prompt** aus. Sie gelangen zur Benutzeroberfläche des Prompt-Generators.
1. Geben Sie in das Textfeld **Anweisungen** `Create a marketing pitch for a product based on a ` ein.
1. Setzen Sie den Cursor an das Ende des von Ihnen eingegebenen Satzes und wählen Sie **Inhalt hinzufügen**.
1. Wählen Sie **Text** aus.
1. Geben Sie im Feld **Name** die Zeichenfolge `draft` ein.
1.  Geben Sie in das Feld **Beispieldaten** `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.` ein und wählen Sie dann **Schließen**.

    ![Screenshot der Benutzeroberfläche des Prompt Builders in Copilot Studio mit einer Eingabevariablen, die mit dem Namen „draft“ konfiguriert wurde.](../Media/prompt-action-input.png)

## Testen und Optimieren Ihres Prompts

1. Wählen Sie **Testen** oberhalb des Feldes mit den Anweisungen, um den Prompt mit den von Ihnen angegebenen Beispieldaten zu testen.
1. Überprüfen Sie die Ausgabe des Testlaufes.

Lassen Sie uns den Prompt optimieren, um eine strukturiertere und konsistentere Ausgabe zu erhalten.

1. Fügen Sie im Textfeld **Anweisungen** den folgenden Text zu den bestehenden Anweisungen hinzu, um den Prompt zu ändern:

    ```The pitch should follow the following Contoso guidelines:
       - Start with a brief hook
       - Describe unique value proposition
       - End with a call-to-action
       - Use an exciting and influential tone
    ```

1. Wählen Sie **erneut Testen** aus, um den Prompt erneut zu testen.
1. Beachten Sie, wie sich die Antwort unterscheidet.
1. Wählen Sie **Speichern**.

## Konfigurieren und Veröffentlichen Ihres Prompts

Nach dem Speichern des Prompts wird das Fenster **Für die Verwendung im Agent konfigurieren** angezeigt.

1. Geben Sie im Feld **Name** den Text `Create a Contoso Marketing Pitch` ein.
1. Geben Sie `Create a marketing pitch that follows Contoso guidelines` im Feld **Beschreibung, damit der Agent weiß, wann dieses Tool verwendet werden soll** ein, und wählen Sie dann **Weiter** aus. Sie werden auf die Seite **Prompt erstellen** weitergeleitet.
1. Wählen Sie **Hinzufügen**.

## (Optional) Hinzufügen einer Promptaktion zu einem Agent

Wenn Sie das vorherige Lab abgeschlossen und einen deklarativen Agent erstellt haben, können Sie diese Aktion Ihrem Agent hinzufügen und die Anweisungen des Agents aktualisieren, um auf die Aktion zu verweisen.

### Hinzufügen des Prompttools

1. Wählen Sie auf der Randleiste in Copilot Studio **Agents** aus.
1. Wählen Sie **Microsoft 365 Copilot** aus.
1. Wählen Sie unter **Agents** den **Produktsupport**-Agent aus, dem Sie die Aktion hinzufügen möchten.
1. Wählen Sie im Abschnitt **Tools** der Seite **Tool hinzufügen** aus.
1. Wählen Sie den Filter **Prompt** aus.
1. Wählen Sie den Prompt **Contoso-Marketingpitch erstellen** aus.
1. Wählen Sie **Zum Agent hinzufügen** aus. Das Tool ist jetzt unter **Tools** im Produktsupport-Agent aufgeführt.

### Konfigurieren des Prompttools

1. Wählen Sie im Abschnitt **Tools** der Übersichtsseite des Agents das Tool `Contoso Marketing Pitch` aus. Sie werden zu einer Seite weitergeleitet, um die Eigenschaften und Einstellungen des Tools zu konfigurieren.
1. Wählen Sie **Eingaben** in der oberen Navigation innerhalb des Prompttools aus.
1. Unter **Zusätzliche Eingänge** wählen Sie **Hinzufügen**.
1. Wählen Sie die Variable **Draft**. Ein Formular wird angezeigt.
1. Stellen Sie sicher, dass das Feld **Wie wird der Agent diese Eingabe ausfüllen** auf **Dynamisch mit der besten Option ausfüllen (Standard)** festgelegt ist.
1. Geben Sie im Feld **Anzeigename** den Namen `Initial draft` ein.
1. Stellen Sie sicher, dass das Feld **Identifizieren als** auf **Die gesamte Antwort des Benutzers** festgelegt ist.
1. Wählen Sie **Speichern** oben rechts im Fenster.

### Ändern der Anweisungen des Agents

Passen Sie die Anweisungen des Agents so an, dass diese Anleitungen für die Verwendung des Prompts enthalten.

1. Fügen Sie im Textfeld **Anweisungen** den folgenden Text zu den vorhandenen Anweisungen hinzu: `Use the Contoso Marketing Pitch action to help marketing stakeholders craft pitches for products based on their draft ideas.`

## (Optional) Testen Ihres Prompttools in Copilot Studio

Testen Sie als Nächstes den Agent mit dem Prompttool in Copilot Studio.

1. Wählen Sie im Bereich**Agent testen** auf der Übersichtsseite Ihres Agents in Copilot Studio die Schaltfläche **Aktualisieren**, um den Testbereich zu aktualisieren und die neuesten Änderungen Ihres Agents zu laden.
1. Geben Sie in das Textfeld für die Testkonversation `Create a Contoso marketing pitch based on the following draft: "Bouncy ball is the hottest product on the market for both youth and adults. It's durable and the largest of its kind."` ein und senden Sie die Nachricht.
1. Überprüfen Sie die Antwort und stellen Sie fest, dass der Agent die Anweisungen befolgt, die Sie in der benutzerdefinierten Eingabeaufforderung angegeben haben.

Sie haben die Übung abgeschlossen und die Funktionalität Ihres Prompttools bestätigt.
