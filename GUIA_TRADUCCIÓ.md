# Guia de Traducció - VSCode Language Pack Valencià

## Introducció

Este document explica com traduir tots els textos de Visual Studio Code al valencià.

## Estructura del Fitxer de Traducció

El fitxer `translations/main.i18n.json` conté totes les cadenes de text que es mostren en VSCode.

### Format

```json
{
  "namespace.key": "Text traduït"
}
```

## Categories Principals

### 1. Editor

- `vs/editor/*` - Tot relacionat amb l'editor de codi

### 2. Workbench

- `vs/workbench/*` - Interfície principal de VSCode

### 3. Extensions

- Menús, barres d'eines, panels

## Com Obtindre TOTS els Textos

Per obtindre el fitxer complet amb TOTS els textos de VSCode:

1. Clona el repositori oficial de traduccions:

```bash
git clone https://github.com/microsoft/vscode-loc.git
```

2. Els fitxers complets estan en:

```
vscode-loc/i18n/vscode-language-pack-<lang>/translations/
```

3. Pots usar el paquet català com a base:

```
vscode-loc/i18n/vscode-language-pack-ca/translations/main.i18n.json
```

## Extensions de VSCode

Cada extensió té el seu propi fitxer de traducció. Per traduir extensions:

1. Crea fitxers addicionals en `translations/extensions/`
2. Afig-los a `package.json` en la secció `translations`

## Publicar l'Extensió

### Prerequisits

```bash
npm install -g @vscode/vsce
```

### Crear Publisher

1. Crea un compte en https://marketplace.visualstudio.com/
2. Crea un Personal Access Token en Azure DevOps
3. Crea un publisher: `vsce create-publisher`

### Empaquetar

```bash
vsce package
```

Açò crea un fitxer `.vsix`

### Publicar

```bash
vsce publish
```

O pujar manualment el `.vsix` al Marketplace.

## Testing

1. Empaqueta l'extensió: `vsce package`
2. Instal·la localment: `code --install-extension vscode-language-pack-ca-va-1.0.0.vsix`
3. Canvia l'idioma: Ctrl+Shift+P > "Configure Display Language" > Valencià
4. Reinicia VSCode

## Recursos

- [Documentació oficial de Language Packs](https://code.visualstudio.com/api/language-extensions/language-pack)
- [Repositori oficial de traduccions](https://github.com/microsoft/vscode-loc)
- [Publishing Extensions](https://code.visualstudio.com/api/working-with-extensions/publishing-extension)
