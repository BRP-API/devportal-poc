# Devportal-poc

Deze documentatie-site is een proof-of-concept (POC) voor een ontwikkelaarsportaal gebaseerd op [Antora](https://antora.org/).

## Overzicht

Dit project bundelt documentatie uit meerdere repositories tot één centrale site. A

## Belangrijkste features
- Multi-repository documentatie met Antora
- Gecombineerde navigatie en zoekfunctionaliteit
- Custom UI bundle
- Automatische build en site-generatie

## Structuur
- `antora-playbook.yml`: Hoofdconfiguratie voor Antora
- `ui.yml`: UI-configuratie en supplemental files
- `.github/workflows/main.yml`: Pipeline voor publiceren op Github Pages

## Gebruikte repositories
De volgende documentatiebronnen worden samengevoegd:

### BRP API
- [brp-api.github.io](https://github.com/brp-api/brp-api.github.io)
- [haal-centraal-brp-bevragen](https://github.com/brp-api/haal-centraal-brp-bevragen)
- [haal-centraal-brp-bewoning](https://github.com/brp-api/haal-centraal-brp-bewoning)

### Berichten API
- ...

## Lokale build
1. Volg de [Install and Run Quickstart](https://docs.antora.org/antora/latest/install-and-run-quickstart/) om de site lokaal te previewen

## UI Bundle
De UI bundle voor deze site bevindt zich in de repository [`antora-ui-bundle`](https://github.com/brp-api/antora-ui-bundle). Deze bundle bevat aangepaste templates, CSS en JavaScript die de standaard Antora UI uitbreiden of vervangen met de huisstijl.

## Aanpassingen doen
- Navigatie aanpassen: Pas navigatie aan in de nav.adoc-bestanden van de content repositories. De navigatie van de BRP-API is opgenomen in de [brp-api.github.io](https://github.com/brp-api/brp-api.github.io) repository.
- Content toevoegen: Voeg de nieuwe documentatiebron toe aan `antora-playbook.yml`

## Meer informatie / Antora Docs
- [Antora documentatie](https://docs.antora.org/)
- [Antora UI aanpassen](https://docs.antora.org/antora-ui-default/)
