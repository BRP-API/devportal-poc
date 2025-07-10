# Devportal-poc

Deze documentatie-site is een proof-of-concept (POC) voor een ontwikkelaarsportaal gebaseerd op [Antora](https://antora.org/).

## Overzicht

Dit project bundelt documentatie uit meerdere repositories tot één centrale site.

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


## Redoc

Om de API-specificatie in Redoc te tonen kun je gebruik maken van de volgende configuratie:

1. Voeg het OpenAPI-bestand toe aan de attachments folder in de module. Bijvoorbeeld: `modules/ROOT/attachments/openapi.yaml`

2. Gebruik onderstaand AsciiDoc-bestand om de API-specificatie met Redoc te tonen:

```adoc
//modules/ROOT/pages/specificatie.adoc
++++
<redoc id='redoc-container'></redoc>
<script src="https://cdn.jsdelivr.net/npm/redoc@2.0.0-rc.64/bundles/redoc.standalone.js"></script>
<script>
  Redoc.init('../_attachments/openapi.yaml', {scrollYOffset: '.toolbar'}, document.getElementById('redoc-container'))
</script>
++++
```

3. Bouw de site lokaal met `antora --fetch antora-playbook.yml` en controleer of Redoc de specificatie correct toont.

## Symlinks

Om symlinks correct te laten werken met Git moet de instelling `core.symlinks` ingeschakeld zijn. Dit kun je instellen met het volgende commando:

```bash
git config --global core.symlinks true
```

Clone eventueel de repository opnieuw.

> [!Note]  
> Je hebt administratorrechten nodig om symlinks aan te maken op Windows.

Meer info: [Git symlinks documentation](https://git-scm.com/docs/git-config#Documentation/git-config.txt-coresymlinks)
