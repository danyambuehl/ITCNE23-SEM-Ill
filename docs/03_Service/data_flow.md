---
layout: default
title: Überwachungsfunktion
parent: Service
nav_order: 2
---

## Überwachungsfunktion

Die Überwachungsfunktion ist die Hauptfunktion der Plattform. Sie überwacht die Website des Unternehmens und benachrichtigt den Benutzer, wenn sich der Inhalt der Website ändert.

Der von mir implementierte Lösungsansatz basiert auf künstlicher Intelligenz (KI) und beinhaltet eine Methode des selbstgesteuerten Lernens. Wenn die KI ein Apartment auf einer Webseite erkennt, wird nicht nur eine Benachrichtigung versendet. Vielmehr sucht die KI mithilfe einer gezielten Frage auch den entsprechenden HTML-Klassenname des Apartments und schreibt diesen in die Datenbank des Unternehmens. Bei zukünftigen Aufrufen der Webseite erkennt die Funktion `find_div_dynamic` dann sofort, ob ein neues Apartment ausgeschrieben wurde.

Auf diese Weise werden Kosten für KI-Anfragen vermieden, da die KI bereits identifiziert hat, wie man ein neues Apartment eigenständig identifizieren kann.

<!-- ## Selbstlernende Funktion

```mermaid
zenuml
      Monitoring-> OpenAI: send changed content
      OpenAI -> OpenAI: check for apartment
      OpenAI -> OpenAI: check for HTML class
      OpenAI -> Database: save HTML class
      OpenAI -> Send_Message: send message
    
    opt {
      Monitoring-> Dynamic_Function: Website hash changed
      Dynamic_Function -> Database: get HTML class
      Dynamic_Function -> Send_Message: send message
    }
``` -->

## Squenz Diagramm

Dieses Sequenz Diagramm zeigt den Ablauf der Überwachungsfunktion.

```mermaid
sequenceDiagram

    participant DB as get_previous_hash_from_db
    participant C as change
    participant FS as find_div_static
    participant FD as find_div_dynamic
    participant PC as ask_chatgpt_about_apartment
    participant U as process_chatgpt_response
    participant AH as ask_chatgpt_about_html_class
    participant PCH as process_chatgpt_response_html_class
    participant SE as send_message_to_me
    participant UC as update_company_record

    DB->>C: 
    Note over C: Has website content changed?
    C->>FS: Hash changed
    FS->>FD: No static div found
    FD->>PC: No dynamic div found
    PC->>U: Ask ChatGPT about apartment
    U->>AH: ask ChatGPT about html class 
    AH->>PCH: process ChatGPT response html class
    PCH->>FD: update found div

    FS -) SE: static div found
    FD -) SE: dynamic div found
    U -) SE: ChatGPT Apartment found
    PCH -) UC: ChatGPT HTML class found
    SE -) UC: Update company record

```

## Flowchart Ablauf

Hier ist der Ablauf der Überwachungsfunktion in einem Flowchart dargestellt.

```mermaid
graph LR
    D[monitor_website] --> get_html
    get_html --> process_html
    process_html --> hash_content
    hash_content --> get_previous_hash_from_db
    get_previous_hash_from_db --> change{Has website content changed?}
    change -->|Yes| find_div_static
    change -->|No| X[End]
    find_div_static -->|Yes| send_message_to_me
    find_div_static -->|No| find_div_dynamic
    find_div_dynamic -->|Yes| send_message_to_me
    find_div_dynamic -->|No| process_chatgpt_response
    send_message_to_me --> update_company_record
    process_chatgpt_response -->|No| update_company_record
    update_company_record --> X
    process_chatgpt_response -->|Yes| send_message_to_me
    process_chatgpt_response -->|Yes| process_chatgpt_response_html_class
    process_chatgpt_response_html_class --> update_company_record
```
