# OpenClaw Runner — packs_canva_pour_petites_entreprises_1__agences

_Généré: 2026-03-06T12:21:24.591772Z_

## Prérequis
- OpenClaw installé et configuré avec une clé API valide
- Fichier présent dans `data/` : `active_niche.json`
- Dossier de sortie : `product_out/packs_canva_pour_petites_entreprises_1_agences/`

## Étape 0 — Charger le contexte produit
```bash
openclaw context load product_out/packs_canva_pour_petites_entreprises_1_agences/01_openclaw_context.json
```

## Remarque importante
- La syntaxe CLI exacte peut varier selon la version d'OpenClaw.
- Ce fichier sert de runner humain/documentaire ; le script Python détecte plusieurs variantes automatiquement.

## Étape 1 — Générer `offer.md`
```bash
# Exemple documentaire seulement — la vraie syntaxe peut varier
openclaw agent --message "[AGENT=offer_builder_agent] produire offer.md au format markdown"
```
**Validation** : Vérifie que les 7 sections sont présentes et que le contenu n'est pas générique.

## Étape 2 — Générer `product_spec.json`
```bash
# Exemple documentaire seulement — la vraie syntaxe peut varier
openclaw agent --message "[AGENT=product_spec_agent] produire product_spec.json au format json"
```
**Validation** : Vérifie que product_type, deliverables et delivery_method sont présents.

## Étape 3 — Générer `sales_page.md`
_Dépend de : offer.md_

```bash
# Exemple documentaire seulement — la vraie syntaxe peut varier
openclaw agent --message "[AGENT=sales_page_agent] produire sales_page.md au format markdown"
```
**Validation** : Vérifie que le CTA et le bloc problème sont présents.

## Étape 4 — Générer `ad_copy.md`
_Dépend de : offer.md_

```bash
# Exemple documentaire seulement — la vraie syntaxe peut varier
openclaw agent --message "[AGENT=ad_copy_agent] produire ad_copy.md au format markdown"
```
**Validation** : Vérifie 10 accroches, 5 corps, 5 headlines.

## Étape 5 — Générer `email_sequences.md`
_Dépend de : offer.md_

```bash
# Exemple documentaire seulement — la vraie syntaxe peut varier
openclaw agent --message "[AGENT=email_sequence_agent] produire email_sequences.md au format markdown"
```
**Validation** : Vérifie que les 5 emails ont chacun un objet, un corps et un CTA.

## Étape 6 — Générer `openclaw_pipeline_spec.json`
_Dépend de : product_spec.json_

```bash
# Exemple documentaire seulement — la vraie syntaxe peut varier
openclaw agent --message "[AGENT=pipeline_spec_agent] produire openclaw_pipeline_spec.json au format json"
```
**Validation** : Vérifie que execution_order et error_handling sont présents.

## Étape 7 — Générer `build_checklist.md`
_Dépend de : product_spec.json, openclaw_pipeline_spec.json_

```bash
# Exemple documentaire seulement — la vraie syntaxe peut varier
openclaw agent --message "[AGENT=checklist_agent] produire build_checklist.md au format markdown"
```
**Validation** : Vérifie que chaque section contient au moins 3 items.