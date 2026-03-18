# Creating, Reading & Modifying Custom JSON Files

To create / read / modify custom JSON files, you would need the following mods:

- [Create JSON File](https://github.com/RatWasHere/bmods/blob/master/Actions/createJsonFile_MOD.js)
- [Read JSON File](https://github.com/RatWasHere/bmods/blob/master/Actions/readJsonFile_MOD.js)
- [Modify JSON File](https://github.com/RatWasHere/bmods/blob/master/Actions/modifyJsonFile_MOD.js)
- [Multi-modify JSON File](https://github.com/RatWasHere/bmods/blob/master/Actions/multiModifyJsonFile_MOD.js)(optional)

## Creating JSON Files

![](https://github.com/slothyacedia/bmd-samples/blob/main/.assets/createJsonFile.png)

First, type in the path where you want to create your JSON file in relation to your project folder.  
i.e If I want `file.json` to be located in `projectFolder/json/file.json`, I would put the path as `json/file.json`.

### Next, type in the content of the JSON file.

For example:

```json
{
  "content": {
    "a": "foo",
    "b": "bar"
  }
}
```

Variables can be inserted by wrapping them with quotes.  
For example:

```json
{
  "content": {
    "a": "${tempVars('foo')}",
    "b": "${tempVars('bar')}"
  }
}
```

### What about lists?

Lists should be wrapped in square brackets `[]`.  
For example:

```json
{
  "list": ["this", "is", "a", "list"]
}
```

For lists that are stored as a variable, just create the list and wrap the variable with quotes.  
For example:

```json
{
  "list": ["${tempVars('list')}"]
}
```

## Reading JSON Files

![](https://github.com/slothyacedia/bmd-samples/blob/main/.assets/readJsonFile.png)
Similar to creating JSON files, type in the path of your JSON file in relation to your project folder.

### Example of JSON file

```json
{
  "content": {
    "a": "foo",
    "b": "bar"
  }
}
```

I would be storing this JSON as a variable `${tempVars('json')}`.  
To access the word `foo`, I can use `${tempVars('json').content.a}` and it will return `foo`.

### What if I already know which element I want from the JSON file?

Lets say you already know what you want to access from the JSON file, you can just type in the element path.  
For example, I want to access the word `bar` from my JSON file, located in `content.b`, I would type `content.b` as the element path.

## Modifying JSON Files

![](https://github.com/slothyacedia/bmd-samples/blob/main/.assets/modifyJsonFile.png)
Similar to creating JSON files, type in the path of your JSON file in relation to your project folder.

Next, select if you're creating/replacing a certain element, or deleting the element.

If you're creating/replacing an element, you would have to type in the content of the element, be it `text`, `nested JSON` or a `list`.

# Additional Features

## Pretty Print

The `Create JSON File` and `Modify JSON File` mods have the option to `pretty print`, meaning that the JSON would be stringified to a more readable version.  
For example, instead of being stored as:

```json
{ "content": { "a": "foo", "b": "bar" } }
```

Enabling pretty print would instead save it as:

```json
{
  "content": {
    "a": "foo",
    "b": "bar"
  }
}
```

## Validating JSON

The `Create JSON File` and `Modify JSON File` mods have a button to `Validate JSON`.  
Clicking the button would do a basic validation of your JSON, letting you know if the content you've typed in is valid or not.

Green - Valid  
Red - Invalid
