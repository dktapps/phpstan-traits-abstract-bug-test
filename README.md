# phpstan-traits-abstract-bug-test

This repository demonstrates an edge case with traits handling in phpstan 0.12.26+.

## TL;DR

`EnchantTable extends Tile` and using `NameableTrait` to fill in abstract methods is OK.
`EnchantTable extends Spawnable` (which in turn extends `Tile`) raises the following FPs:
```
 ------ ---------------------------------------------------------------------------------------------------------------------------
  Line   EnchantTable.php
 ------ ---------------------------------------------------------------------------------------------------------------------------
  26     Non-abstract class pocketmine\tile\EnchantTable contains abstract method readSaveData() from class pocketmine\tile\Tile.
  26     Non-abstract class pocketmine\tile\EnchantTable contains abstract method writeSaveData() from class pocketmine\tile\Tile.
 ------ ---------------------------------------------------------------------------------------------------------------------------

 [ERROR] Found 2 errors
```
