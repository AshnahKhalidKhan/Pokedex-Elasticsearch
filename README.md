# Pokedex-Elasticsearch
A fun visualization of Elasticsearch using Pokémon.

### Things to feel proud of that I learned when I feel like engineering is not for me:
- `python -m venv venv`
- `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`
- `venv\Scripts\activate`
- `pip install fastapi uvicorn elasticsearch requests`
    What each library is:
    - fastapi — the web framework we'll use to build our API. Industry standard for modern Python backends.
    - uvicorn — the server that runs FastAPI. FastAPI can't run alone, it needs a server.
    - elasticsearch — the official Python client for talking to Elasticsearch
    - requests — for fetching Pokémon data from PokéAPI
- `ASGI (Asynchronous Server Gateway Interface)`: Imagine you're building a phone. The phone manufacturer and the phone network need to agree on a standard — what size SIM card, what signal protocol — so any phone works with any network. Without that standard, every phone would only work with one specific network. ASGI is that standard for Python web apps. It defines the rules for how a Python web application and a server communicate with each other. FastAPI speaks ASGI, Uvicorn speaks ASGI, so they snap together perfectly. If tomorrow a faster server than Uvicorn comes along that also speaks ASGI, you could swap it in without touching your FastAPI code at all.
- FastAPI handles traffic coming into your backend from the browser. Requests handles traffic going out of your backend to somewhere else — in our case, PokéAPI. The flow looks like this:
```
Browser → FastAPI → Requests → PokéAPI
                 ↑                 ↓
               results ←←←←←←←←←←←
```
- 