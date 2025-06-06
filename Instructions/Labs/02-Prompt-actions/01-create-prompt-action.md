---
lab:
  title: '2.1: Erstellen einer Promptaktion'
---

# Erstellen einer Promptaktion

In dieser Übung erstellen Sie eine Promptaktion, testen den Prompt in Copilot Studio und testen den Prompt in einem Copilot Agent. Sie erstellen eine Promptaktion, die den Benutzenden hilft, ihre bloßen Ideen in organisierte Marketingvorschläge zu verwandeln, die einem bestimmten Format und Richtlinien folgen.

Diese Übung dauert ca. **15** Minuten.

## Erstellen einer Promptaktion in Copilot Studio

1. Öffnen Sie Copilot Studio in Ihrem Webbrowser, indem Sie zu [Copilot Studio](https://copilotstudio.microsoft.com) navigieren unter `https://copilotstudio.microsoft.com`.
1. Wählen Sie **Bibliothek** in der linken Navigation.
1. Wählen Sie **Neu hinzufügen** und wählen Sie dann **Prompt**. Der **Assistent zum Hinzufügen einer Promptaktion** öffnet sich.
1. Geben Sie in das Feld **Aktionsname** `Create a Contoso Marketing Pitch` ein.
1. Geben Sie in das Feld **Beschreibung** `Create a marketing pitch that follows Contoso guidelines` ein und wählen Sie **Weiter**. Sie werden auf die Seite **Prompt erstellen** weitergeleitet.
1. Geben Sie in das Textfeld **Anweisungen** `Create a marketing pitch for a product based on a ` ein.
1. Setzen Sie den Cursor an das Ende des von Ihnen eingegebenen Satzes und wählen Sie **Inhalt hinzufügen**.
1. Wählen Sie **Text** aus.
1. Geben Sie im Feld **Name** die Zeichenfolge `draft` ein.
1. Geben Sie in das Feld **Beispieldaten** `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.` ein und wählen Sie dann **Schließen**.

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

## Konfigurieren und Veröffentlichen Ihrer Aktion

1. Geben Sie auf der Seite **Aktionsparameter auswählen** die folgende **Beschreibung** für die `draft`-Eingabevariable ein: `initial draft of the marketing pitch`.
1. Geben Sie die folgende **Beschreibung** der `text`-Ausgabevariable an: `Final marketing pitch that adheres to Contoso guidelines`.
1. Wählen Sie **Weiter** aus.
1. Vergewissern Sie sich, dass Sie die Details korrekt eingegeben haben und wählen Sie **Veröffentlichen**.
1. Warten Sie einige Augenblicke, während Ihre Aktion gespeichert und veröffentlicht wird.
1. Ihre Aktion ist jetzt in der Bibliothek verfügbar. Klicken Sie auf **Speichern und schließen**.

   > **Hinweis**: Es kann einige Minuten oder länger dauern, bis Ihre neue Promptaktion in den Abschnitten **Empfohlen** oder **Bibliothek** auf der Seite **Aktion hinzufügen** eines Agents erscheint.

## (Optional) Hinzufügen einer Promptaktion zu einem Agent

Wenn Sie das vorherige Lab abgeschlossen und einen deklarativen Agent erstellt haben, können Sie diese Aktion Ihrem Agent hinzufügen und die Anweisungen des Agents aktualisieren, um auf die Aktion zu verweisen.

### Hinzufügen der Aktion

1. Wählen Sie in der **Bibliothek** den deklarativen Agent aus, dem Sie die Aktion hinzufügen möchten.
1. Wählen Sie im Abschnitt **Details** die Option **Bearbeiten**.
1. Fügen Sie im Textfeld **Anweisungen** den folgenden Text zu den vorhandenen Anweisungen hinzu: `Use the Contoso Marketing Pitch action to help marketing stakeholders craft pitches for products based on their draft ideas.`
1. Wählen Sie auf der Detailseite des Agents unter **Aktionen** die Option **Aktion hinzufügen**.
1. Wählen Sie in den Abschnitten **Empfohlen** oder **Bibliothek** des modalen Fensters **Aktion hinzufügen** die Option **Contoso Marketing Pitch**.
1. Stellen Sie auf der Aktionsseite sicher, dass der **Name** `Create a Contoso Marketing Pitch` lautet.
1. Stellen Sie sicher, dass die **Beschreibung** `Create a marketing pitch that follows the Contoso guidelines` lautet.
1. Wählen Sie **Aktion hinzufügen** aus. Dies kann einige Zeit dauern. Die Aktion wird der Liste der für den Agent verfügbaren Aktionen unter **Aktionen** hinzugefügt.

### Konfigurieren einer Aktion

1. Wählen Sie die Aktion `Contoso Marketing Pitch` aus den für den Agent verfügbaren Aktionen. Sie werden zu einer Seite weitergeleitet, um die Eigenschaften und Einstellungen der Aktion zu konfigurieren.
1. Vergewissern Sie sich, dass der **Aktionsname** auf `Create a new Contoso marketing pitch` festgelegt ist.
1. Wählen Sie **Eingaben** in der oberen Navigation innerhalb der Aktion.
1. Unter **Zusätzliche Eingänge** wählen Sie **Hinzufügen**.
1. Wählen Sie die Variable **Draft**. Ein Formular wird angezeigt.
1. Stellen Sie sicher, dass das Feld **Wie wird der Agent diese Eingabe ausfüllen** auf **Dynamisch mit der besten Option ausfüllen (Standard)** festgelegt ist.
1. Geben Sie im Feld **Anzeigename** den Namen `Initial draft` ein.
1. Stellen Sie sicher, dass das Feld **Identifizieren als** auf **Die gesamte Antwort des Benutzers** festgelegt ist.
1. Wählen Sie **Speichern** oben rechts im Fenster.

## (Optional) Testen Ihrer Promptaktion in Copilot Studio

Als Nächstes testen Sie den Agent mit der Aktion in Copilot Studio.

1. Wählen Sie im Bereich**Agent testen** auf der Übersichtsseite Ihres Agents in Copilot Studio die Schaltfläche **Aktualisieren**, um den Testbereich zu aktualisieren und die neuesten Änderungen Ihres Agents zu laden.
1. Geben Sie in das Textfeld für die Testkonversation `Create a Contoso marketing pitch based on the following draft: "Bouncy ball is the hottest product on the market for both youth and adults. It's durable and the largest of its kind."` ein und senden Sie die Nachricht.
1. Überprüfen Sie die Antwort und stellen Sie fest, dass der Agent die Anweisungen befolgt, die Sie in der benutzerdefinierten Promptaktion angegeben haben.

Sie haben die Übung abgeschlossen und die Funktionalität Ihrer Promptaktion validiert.
