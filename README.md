# NotEnoughUpdates-2.0.0-Fixed
NotEnoughUpdates (NEU) but i fixed /neuah divine error

## What was the error
When you do /neuah, you have a option to filter the rarity of whatever you want to search. Between the rarities, there was a specific one called "Divine" that, when you chose it, the game crashes.
I really don't know WHY this happens but anyways, I fixed it by removing it :) (using bytecode 💪)

![image](https://user-images.githubusercontent.com/93355393/153053917-f7163e4d-5274-4d13-bb7d-bb5ba9bc2f0f.png)

## How did you removed it
Simple! Using JByteCustom, my own customized JByteMod made by GraxCode and some other devs, sorry I can't remember.
![image](https://user-images.githubusercontent.com/93355393/153054124-887f3c85-8614-43b6-921a-2ab169a68d8f.png)<br>
Before the modification, there was a bipush 10, that was the size of the array that contains the "divine" rarity, so as I removed the "divine" rarity, I just decreased the array size to 9.

## Changes

### Before:
```java
rarityArr = new java.lang.String[]{"COMMON", "UNCOMMON", "RARE", "EPIC", "LEGENDARY", "MYTHIC", "SPECIAL", "VERY SPECIAL", "SUPREME", "DIVINE"};
```

### Now:
```java
rarityArr = new java.lang.String[]{"COMMON", "UNCOMMON", "RARE", "EPIC", "LEGENDARY", "MYTHIC", "SPECIAL", "VERY SPECIAL", "SUPREME"};
```

### Before:
```java
[...]
  stringArray[8] = net.minecraft.util.EnumChatFormatting.DARK_RED + net.minecraft.util.EnumChatFormatting.BOLD.toString() + "SUPREME";<br>
  stringArray[9] = net.minecraft.util.EnumChatFormatting.AQUA + net.minecraft.util.EnumChatFormatting.BOLD.toString() + "DIVINE";
```
### Now:<br>
```java
[...]
  stringArray[8] = net.minecraft.util.EnumChatFormatting.DARK_RED + net.minecraft.util.EnumChatFormatting.BOLD.toString() + "SUPREME";<br>
```
<br>
### Before:
```java
[...]
  rarityArrMap.put((java.lang.Object)"SUPREME", (java.lang.Object)rarityArrC[8]);<br>
  rarityArrMap.put((java.lang.Object)"DIVINE", (java.lang.Object)rarityArrC[9]);<br>
```
### Now:
```java
[...]
  rarityArrMap.put((java.lang.Object)"SUPREME", (java.lang.Object)rarityArrC[8]);
  ```
