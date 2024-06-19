---
layout: default
title: Testing
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

### Pipline SAST Testing

Ich habe eine einfache Pipeline erstellt, die die Sicherheit des Codes überprüft.

![GitLab Pipeline](../img/testing/pipline_sast1.png)

Bei der Überprüfung des Codes wurden eine kleine Sicherheitslücken gefunden.

[Service](../img/testing/gl-sast-report.json){: .btn }

Folgenden Fehler wurden gefunden:

```json
"description":"The application was found using the `requests` module without configuring a timeout value for\nconnections"
```

Nachdem ich die Fehler behoben habe, wurde die Pipeline erfolgreich durchgeführt.

[Service](../img/testing/gl-sast-report2.json){: .btn }

### Pytest Testing

Ich habe einige Pytest-Tests geschrieben, um die Funktionen zu überprüfen.

![Pytest](../img/testing/py_testingpng.png)

### Pytest Coverage Testing

**app/apartments/routes.py**

Das Coverage für routes.py in Apartments ist bei 0%.

Da die Apartments routes soweit nur als code geschrieben wurden jedoch noch nicht verwendet wird und die vollständige Implementierung für den nächsten Sprint geplant ist.

```python
# app/__init__.py
    # Register blueprints here
    from app.companies import bp as companies_bp
    app.register_blueprint(companies_bp, url_prefix='/companies')

    # from app.apartments import bp as apartments_bp
    # app.register_blueprint(apartments_bp, url_prefix='/apartments')

    from app.users import bp as users_bp
    app.register_blueprint(users_bp, url_prefix='/users')
```

**openai.py**

Es hat viele Exception handling tests die ich nicht explizit getestet habe da es zu viele sind.

Die Coverage für openai.py ist 58%. Da die ganzen exceptions nicht getestet wurden.

```python
def ask_chatgpt_about_apartment(html_content):
    try:
        response = client.chat.completions.create(
            model="gpt-4o",
            messages=[
                {"role": "system", "content": "You are a helpful assistant skilled in parsing HTML content."},
                {"role": "user", "content": f"Check if there are new apartments listed in the following HTML content:\n{html_content} and respond in the format 'yes apartment found or no apartment found'."}
            ],
            max_tokens=500,
            timeout=60
        )
        logger.info(f"ChatGPT response for ask_chatgpt_about_apartment: {response.choices[0].message.content.strip()}")
        return response.choices[0].message.content.strip()
    except openai.APIConnectionError as e:
        logger.error("The server could not be reached")
        logger.error(e.__cause__)
    except openai.RateLimitError as e:
        logger.error("A 429 (RateLimitError) status code was received; we should back off a bit.")
        time.sleep(time_to_wait)  # wait before retrying
    except openai.APIStatusError as e:
        logger.error("Another non-200-range status code was received")
        logger.error(e.status_code)
        logger.error(e.response)
```

