Welcome to the WorldGuard Tutorial (Port of [WorldGuard for Bukkit!](https://github.com/sk89q/WorldGuard))!
Here you'll find how you can make use of this feature-rich plugin.

WorldGuard lets you and players guard areas of land against griefers and undesirables, as well as tweak and disable various gameplay features of Minecraft (PocketMine in general).

**Command:** "/region"

**Permission:** ` worldguard.create`, `worldguard.modify`, `worldguard.delete`

**Alias:** "/rg"

### Creating a region
If you aren't OP on your server, you must find a way to give yourself the permission: `worldguard.create`. This can be done through permission-management plugins such as PurePerms.

Command: `/region create <region-name>`

Now you will have to select two points to create the region. The region is specified as the area between the two points (cube/cuboid). Congratulations, you've created your first region! You can create as many regions as you like.

### Managing a region
Now that you've created your region, you would want to manage it. There are many flags you can play with, for this. You can get a list of region flags using the command `/region flags get <region-name>`.

#### Toggle PvP
You can disable Player v. Player damage by using the command `/region flags set <region-name> pvp false`. You can re-enable pvp by using `/region flags set <region-name> pvp true`.

#### Toggle Terrain Modification (Block breaking, Block placing, ...etc)
To deny players from modifying a certain region, you can disable the "editable" flag by using the command `/region flag set <region-name> editable false`.

#### Region-based effects
To give a player effects when they join a region, use `/region flags set <region-name> effects <effect-id> <effect-amplifier>`. The effect duration is infinity and is gone once the player quits the region. To give player speed 2 and jump 3 on joining a region, you can use...

`/region flags set <region-name> effects 1 2`,

`/region flags set <region-name> effects 8 3`

#### Blocking specific commands
You can block specific commands in specific regions by using the command `/region flags set <region-name> blocked-cmds <command>`. Example to block command `/give` and `/op` in a region:

`/region flags set <region-name> blocked-cmds /give`,

`/region flags set <region-name> blocked-cmds /op`

#### Allow specific commands
You can allow usage of certain commands in a specific region by using the command `/region flags set <region-name> allowed-cmds <command>`. Example to allow command `/give` and `/op` in a region:

`/region flags set <region-name> allowed-cmds /give`,

`/region flags set <region-name> allowed-cmds /op`

This will allow the use of `/give` and `/op` only, in `<region-name>`. No other commands can be used other than these.

#### Enable opening doors, trapdoors, chests, hoppers etc.
To do this, you can enable the "use" flag for the region. When "use" is set to true, players will be able to interact with such blocks.

#### Toggle item drops
To allow/disallow item dropping in a region, you can set the flag "item-drops" to true or false by using the command `/region flags set <region-name> item-drops true`.

#### Disable explosion
To disable explosion in a region, set the flag "explosion" to false. You can set it to true if you want to enable it.

#### More Flags
* **notify-enter**: Send a message when player enters a region. Usage: `/region flags set <region-name> notify-enter Hello, you have entered this region.`
* **notify-leave**: Send a message when player leaves a region. Usage: `/region flags set <region-name> notify-leave Hello, you have left this region.`
* **allowed-enter**: Allow/disallow players from entering a region. Set this flag to true or false.
* **allowed-leave**: Allow/disallow players from leaving a region. Set this flag to true or false.
* **whitelist**: Add player to whitelist. Usage: `/region flags set <region-name> whitelist muqsitrayyanxo`
* **fly-mode:** Let players fly in the region
* * 0 => Shows vanilla behaviour.
* * 1 => Flight mode enabled.
* * 2 => Flight mode disabled.
* * 3 => Flight mode enabled, but is disabled once the player leaves the region.
* **enderpearl**: Allow/disallow use of ender parks (true/false).
* **send-chat**: Allow/disallow players to chat (true/false).
* **receive-chat**: Allow/disallow players from receiving chat (true/false).
* **game-mode**: Set a region's game-mode. (0, 1, 2, 3)
#### Reset a flag of a region to default value.
`/region flags reset <region-name> <flag>`

#### 