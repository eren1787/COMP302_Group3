## Operation Contract 9 - consumeItem(item) (Use Case 9)

Pre: Item is a consumable in inventory or adjacent.
Post: The stat named by the item's effect changed by its amount, at most the stat maximum, item removed from inventory or map.

## Operation Contract 10 - equip(item) (Use Case 10)

Pre: Item has EQUIP and in inventory 
Post: Previously equipped item is unequipped if any, new item equipped is true, if item is armor new shield is base + shield armor.

## Operation Contract 11 - attackEnemy(enemy) (Use Case 11)

Pre: Melee weapon equipped, enemy within adjacent tiles, energy>0, no attack timer wait.
Post: Hero energy decreased, enemy hp decrease, if enemy hp<=0 enemy removed, kills increased, a drop based on drop chance.

## Operation Contract 12 - fire(targetCell) (Use Case 12)

Pre: Ranged weapon equipped with charge>0, enough Energy, no attack timer wait.
Post: A line created from Hero's cell towards target cell; weapon charge decreased by 1; energy decreased.
