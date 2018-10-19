# Scoreboards
**Scoreboards is a PocketMine-MP plugin that helps creatings scoreboards in MPE 1.7!**

## Installation
 - You can get the compiled `.phar` in releases by clicking [here](https://github.com/TwistedAsylumMC/Scoreboards/releases)
 - Add the `.phar` to your `/plugins` directory & restart your server.
 > Note: This plugin only works on MCPE 1.7 and above, tested on PocketMine-MP 3.3.0
 
 ## Usage
 You'll need to import the `Scoreboards\Scoreboards.php` class. This is the main class and probably the only class you'll need for creating Scoreboards.
 ```php
 <?php
 use Scoreboards\Scoreboards;
 ```
 
 ### Creating an instance
 In the small documentation, `$api` will be used to refer to an instance of Scoreboards. You can create an instance by doing:
```php
$api = Scoreboards::getInstance();
``` 
 
### Creating a Scoreboard
`$api::new()` creates a new Scoreboard with an objective name, display name and then sends it to a player.
```php
/** @var Player $player */
$api->new($player, "ObjectiveName", "Title that is displayed in game");
```
`$api::remove()` removes a Scoreboard from a player. You do not need to enter an objective name as it is stored from `$api::new()`.
```php
/** @var Player $player */
$api->remove($player);
```
`$api::setLine()` sets a line's text. This only works if the player has a scoreboard sent to them. The `1` is the line, and can go up to `15`.
```php
/** @var Player $player */
$api->setLine($player, 1, "Line Text");
```
`$api::getObjectiveName` returns a string of the Player's objective name from their scoreboard, returns null if the player does not have a scoreboard.
```php
/** @var Player $player */
$api->getObjectiveName($player);
```

To update an existing scoreboard, you can simply use `$api::new()` again, and it will remove the Player's existing one, and add the new one.