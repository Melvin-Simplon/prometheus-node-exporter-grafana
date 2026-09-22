# Monitoring d'une machine avec Prometheus, node_exporter et Grafana

## Résumé

Vous devez monitorer l'état d'une machine, et exporter les metrics vers un serveur prometheus que vous aurez déployé au préalable.

## Déroulé type

1. **Lancer un serveur prometheus** (30mn) : Utilisez leur image officielle, sans configuration particulière. Puis vérifier le setup en accédant à la console, et en vérifiant la réponse de l'endpoint `/metrics` (oui oui, prometheus lui-même expose ses propres metrics...)
2. **Lancer un exporteur de metrics** (1h) : Utilisez le `node_exporter` pour exposer les metrics de votre machine. Vérifiez qu'il soit bien accessible.
3. **Configurer prometheus** (30mn) : Indiquez à prometheus comment "scraper" les metrics exposées par l'exporteur.
4. **Effectuer des requêtes dans prometheus** (30mn) : Constatez la présence de vos metrics dans prometheus en effectuant quelques requêtes de test.
5. **Deployer Grafana pour visualiser les données** (30mn) : Utilisez leur image officielle également.
6. **Connecter Grafana à Prometheus** (30mn) : Ajouter une "data source" dans Grafana, qui pointe vers le serveur prometheus.
7. **Importer un dashboard dans Grafana** (30mn) : Importer un dashboard existant, par exemple "Node Dashboard".
   - **OU Créer votre propre dashboard** (plus long) : Créez vos propres graphiques et requêtes prometheus.

## Conseils

- Bien comprendre le pattern du "metrics exporter"
- Comprendre le fonctionnement de prometheus en mode "pull"
- Comprendre les notions de Data Source, Dashboards et Charts dans Grafana

## Bonus

Faire un deuxième prometheus stateless, en mode pull-push vers le prometheus principal.
