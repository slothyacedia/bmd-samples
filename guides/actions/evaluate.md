# Evaluate

![](https://github.com/slothyacedia/bmd-samples/blob/main/.assets/evaluate.png)

## What does evaluate do?

`Evaluate` runs Javascript code.

## Example

```js
let approvedServers = bridge.variables[`approvedServerList`]
let allServers = bridge.variables[`botGuildIds`]

unapprovedServers = allServers.filter((server) => !approvedServers.includes(server))
```

What this does is that it references 2 temporary variables and filters for servers that are not in the `approvedServers` list.

## Referencing Variables

To reference `Temporary` variables;

```js
let foo = bridge.variables["..."]
```

To reference `Server` variables;

```js
let foo = bridge.data.serverVars["serverId"]["..."]
```

To reference `Global` variables;

```js
let foo = bridge.data.globalVars["..."]
```

## Storing Variables

To store `Temporary` variables;

```js
let bridge.variables["..."] = value
```

To store `Server` variables;

```js
let bridge.data.serverVars["serverId"]["..."] = value
```

To store `Global` variables;

```js
let bridge.data.globalVars["..."] = value
```

## Using Stored Variables

The ["..."] would be the name of the variable, so for example;

```js
let bridge.variables["foo"] = "bar"
```

Then access the variable like this;

```js
${tempVars('foo')} // "bar"
```

## Whats the difference between `Execute` and `Evaluate`?

`Execute ` - Runs **operating system** commands.

`Evaluate` - Run **Javascript** code.
