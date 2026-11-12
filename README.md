# metaltura/domain

Le métamodèle de domaine de la librairie metaltura : ce qu'on décrit d'un métier avant de choisir une technologie. Les patrons des autres dépôts partent d'un modèle de domaine pour écrire une application.

## Ce qu'il contient

- `models/Domain.yaml` — le métamodèle de domaine (PLAT-76) : Entity · Field · EntityRelation · Invariant · Lifecycle · State · Transition · Service · Operation · Process · Step · Branch. Une Entity est un `Core:Type` · ses Field et ses EntityRelation sont des `Core:Feature` (PLAT-231) : le code d'une opération voit les champs et les relations d'une entité. Une EntityRelation nomme l'entité visée par `type`. `extends` est une relation d'héritage pour la plateforme (`supertype` · PLAT-254) : le type d'une entité reçoit aussi les champs et les relations de ses ancêtres · `commande.numero` vient de `Document`. Son diagramme de classes est `DomainClassDiagram`.

Un diagramme est un élément du modèle qu'il montre. Il est rangé à la racine du modèle, ou dans le paquet qu'il décrit quand il en décrit un seul.

## Ce dont il dépend

D'aucun autre dépôt de la librairie. `Domain` ne nomme que `Diagram` et `Uml`, des modèles système de Metaltura : leur nom seul suffit.

## L'utiliser depuis un autre dépôt

Un modèle qui instancie le domaine ou un patron qui le lit écrit dans sa liste `depends` :

```yaml
depends:
  - metaltura/domain/Domain@v2.0.0
```

Metaltura clone ce dépôt à l'étiquette `v2.0.0` à l'ouverture de l'espace de travail. Toute la librairie est à `v2.0.0` : Metaltura refuse qu'un même dépôt soit demandé à deux versions.

## D'où il vient

Ce dépôt vient du dépôt privé `Kogitec/simple-mda`, `main` à `96a1a75` (PLAT-1461), rangé par sujet par PLAT-1498 en un seul commit. L'historique de ses fichiers reste dans `simple-mda`, archivé.
