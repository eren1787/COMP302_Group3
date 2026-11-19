# Use Case 9 - Consume Item 

Primary actor: Player 
Preconditions: There is a consumable item in the inventory or on a adjacent tile.
Postconditions: Stats are changed accordingly, item is gone.

## Main Flow 
1. Player selects DRINK.
2. System executes the DRINK action and gives the stats to character.
3. System removes the item from the inventory.
4. Stats bars are updated accordingly.

## Subscenarios
1a. If consumable item is on the ground, TAKE should be performed first. 
2a. Stat is already full. System may ask "Stat already full. Do you still want to consume?" with a yes/no screen. Based on the decision item is consumed or not.

# Use Case 10 - Equip Item

Primary Actor: Player
Preconditions: There is a item with EQUIP in the inventor or on a adjacent tile.
Postconditions: One weapon or armor is equipped. 
 
## Main Flow
1. Player selects EQUIP on a weapon/armor in the inventory.
2. Systems unequips current weapon/armor if there is any.
3. System marks the new weapon/armor as equipped.
4. If the equipped item is an armor, shield stat is updated as current base shield + armor stat.

## Subscenarios
1a. If armor/weapon is on the ground, TAKE should be performed first.
1b. If item is on a power cell and equipped item is a ranged weapon, ranged weapon is charged. If charge is full or equipped item is not a ranged weapon
    then player stores the power cell. 

# Use Case 11 - Attack Enemy

Primary Actor: Player
Preconditions: Player equipped a melee weapon, enemy in 3x3 area near player, Energy>0, Attack timer resetted.
Postconditions: Enemy HP reduced or enemy slain.

## Main Flow
1. Player clicks on adjacent enemy. 
2. System checks weapon, energy and attack timer. 
3. System substracts energy from player and set timer.
4. System calculates damage, substracts the enemy's natural armor and shield.
5. System reduces enemy HP, updates statistics and plays a hit sound. 
6. If HP <= 0, system removes enemy, kills increase, and a drop may appear if decided by devs.

## Subscenarios
1a. If no weapon equipped, system notifies with a "no weapon equipped".
1b. If enemy is not adjacent, system notifies with a "too far".
2a. If no energy or waiting for timer, system ignores attack.

# Use Case 12 - Fire a Ranged Weapon

Primary Actor: Player
Preconditions: Player equipped a ranged weapon with charge>0, player has enough energy, attack timer resetted.
Postconditions: Shot refused by system or bullet travels in a line to clicked cell.

## Main Flow
1. Player clicks on anywhere on the map.
2. System checks a ranged weapon with charge>0, player has enough energy, attack timer resetted.
3. System substracts energy from player, set timer, reduces weapon charge by 1.
4. Weapon bullet travels the line from player to clicked cell. It stops on a wall, static object, map edge or character.
5. If hit an enemy, system calculates damage, substracts the enemy's natural armor and shield.
6. System reduces enemy HP, updates statistics and plays a hit sound. 
7. If HP <= 0, system removes enemy, kills increase, and a drop may appear if decided by devs.

## Subscenarios
2a. Weapon charge is 0, system displays "out of charge".
5a. Enemy hit before shot reached, bullet continues.
