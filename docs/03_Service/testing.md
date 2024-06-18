---
layout: default
title: testing
parent: Service
nav_order: 4
---

## Manuelle Tests

Hier werden einige Manuelle Tests durchgeführt um die Funktionen zu überprüfen.

![Testing](../img/testing.png)

| Description | Test Step | Expected Result | Status | Screen |
| ---         | ---       | ---             | ---    |  ---   |
| `find_div_dynamic`| Wohung mit der find_div:dynamic finden und informieren | find_div_dynamic success log and message send  | true | [Screenshot](../img/testing/find_div_dynamic.png) |
| `find_div_dynamic`| Neue Class Name gleiches Ziel für find_div_dynamic | find_div_dynamic neuer classnam success log and message send  | Device Paused | [Screenshot](../img/testing/find_div_dynamic2.png) |
| `find_div_dynamic`| Neue Class Name aus Datenbank auslesen | grid-item wohnung22  | grid-item wohnung22 | [Screenshot](../img/testing/find_div_dynamic3.png) |
| `no changes`| keine Änderungen auf Website | gleicher hash kein update  | erfolgreich | [Screenshot](../img/testing/same_hash.png) |
| `changes`| Änderungen auf Website | neuer hash update  | erfolgreich | [Screenshot](../img/testing/new_hash.png) |
| `find apartment` | Wohnung finden mit ChatGPT | Yes, there is at least one new apartment listed in the HTML content  | erfolgreich | [Screenshot](../img/testing/chat_gpt_response.png) |
| `find html class` | HTML Class Name finden mit ChatGPT | ask_chatgpt_about_html_class: HTML Tag: <div>, Full Class Name: grid-item wohnung11  | grid-item wohnung22 | [Screenshot](../img/testing/chat_gpt_response_html.png) |
| `update company record` | Update Company Record class_name | grid-item wohnung11  | erfolgreich | [Screenshot](../img/testing/chat_gpt_response_html_updatet.png) |

## Automatisches Testing

Hier werden einige Automatische Tests durchgeführt um die Funktionen zu überprüfen.

![Testing](../img/testing.png)