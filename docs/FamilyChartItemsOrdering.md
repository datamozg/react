# Family diagram items ordering
Family diagram supports multiple parents and children per node, so there is no deterministic way to define groups of items and their order inside of the group, so family diagram provides non-determenistic API to order items. That means if items expected to be in one layout group then user can use following properties to guide layout engine about user preferred relative order of items:

1. `relativeItem` - item position and placement type defined relative to this property referenced item
2. `placementType` - item placement on the left or right side of relative item. Property has following values:
    * `primitives.common.AdviserPlacementType.Left`
    * `primitives.common.AdviserPlacementType.Right`
3. `position` - if several items reference the same `relativeItem` and placement then this `position` property defines order of them.

This relative optional ordering approach gives none ordered nodes to be placed optimally, so if item has no relative item defined then layout engine will try to find the best place for it based on its relations.

Please, pay attention that loops in references are completely ignored, so don't create mutual references between items.

## Family Items Ordering Sample

[React](../src/Samples/FamilyChartItemsOrdering.js)

## Multiple Families Ordering Sample

[React](../src/Samples/MultipleFamiliesOrdering.js)