### libpf (ProfanityFilter Library)
This is a based virion api plugin for developers.<br>
Use [DeVirion](https://poggit.pmmp.io/p/DeVirion) or [VirionTool](https://poggit.pmmp.io/p/VirionTool) to inject the code or download this source code.<br>

# How to use the code?
An [example plugin](https://github.com/ReinfyTeam/ProfanityFilter-ExamplePlugin) can give you an example of basic usage of api.<br>
1. Import the class first.
   ```php
   use ReinfyTeam\libpf\ProfanityFilter;
   ```
2. Import the chat event class & write the following:
   ```php
   use pocketmine\event\Listener;
   use pocketmine\event\player\PlayerChatEvent;
   ```
   ```php
   public function onChat(PlayerChatEvent $event) : void{ // the function event
         if(ProfanityFilter::detectProfanity($event->getMessage(), ["test"])){
                 $event->cancel(); // cancel the chat event
                 $event->getPlayer()->sendMessage("§cPlease Watch your language!"); // the warning message
         }
   }
   ```
- Removing the unicode messages
  You can use the following:
  ```php
  ProfanityFilter::removeUnicode($message, false); // This removes ONLY non-printable characters like ®
  ProfanityFilter::removeUnicode($message, true); // This removes non-printable AND other mcpe characters such as emoji.
  ```
- You can use default profanity list by:
  ```php
  ProfanityFilter::defaultProfanity(); // returns array can be used as:

  ProfanityFilter::detectProfanity($message, ProfanityFilter::defaultProfanity());
  ```
<p align="right">Made by <a href="https://github.com/ReinfyTeam">ReinfyTeam</a> :heart:</p>
