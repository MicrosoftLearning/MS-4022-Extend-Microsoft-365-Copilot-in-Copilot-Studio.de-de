---
title: Übungsanweisungen
permalink: index.html
layout: home
---

# Übungen

Auf dieser Seite sind Übungen aufgeführt, die dem folgenden Microsoft-Qualifikationskurs zugeordnet sind **MS-4022: Erweitern von Microsoft 365 Copilot in Copilot Studio**.

Verwandter Lernpfad: [Erweitern von Microsoft 365 Copilot in Copilot Studio](https://learn.microsoft.com/training/paths/extend-microsoft-365-copilot-studio/).

**Hinweis**: Um diese Übungen abzuschließen, benötigen Sie Folgendes:

- Ein Geschäfts-, Schul- oder Unikonto mit [Zugriff auf Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/requirements-licensing-subscriptions). Wenn Sie je nach Konfiguration Ihrer Microsoft 365-Organisation noch keinen Zugriff auf Copilot Studio haben, können [Sie möglicherweise ein Testkonto](https://learn.microsoft.com/microsoft-copilot-studio/sign-up-individual) erstellen.
- Eine Microsoft 365 Copilot-Lizenz
- Anmeldeinformationen, die für die Verbindung mit den gewünschten Inhaltsquellen (Connectoren, APIs usw.) erforderlich sind

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% assign labs = labs | sort: "lab.title" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}

