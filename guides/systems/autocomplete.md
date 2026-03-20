# Autocomplete

When using slash commands, a option in parameters is the "Autocomplete" toggle.

To use autocomplete, you need to return a list.

Lets do something simple, like basic searching within a list of items.

## Guide

Lets create a list of items, lets say

```json
["Table", "Wooden Table", "Metal Table", "Chair", "Wooden Chair", "Metal Chair", "Plate", "Wood Plate", "Metal Plate"]
```

This will be our list of items that we can search through [itemList]

Now, lets search for items that contain the word "wood" in them.

1. Store the user input

   > Open the autocomplete menu and give the user input a variable [userInput]

2. Match

   > Use the `filter list` modded action and set it up to filter for elements that contain the word "wood" (case insensitive)
   > Store the filtered list as a variable [filteredList]

3. Return result [filteredList]
   > On the client side, it should show options like "Wooden Table", "Wooden Chair", "Wood Plate"
