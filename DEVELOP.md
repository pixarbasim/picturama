How to develop Ansel
====================


Build from sources
------------------

```bash
npm i
npm start
```

If you get an error with `node-gyp rebuild` then delete `~/.node-gyp` and try again:

```bash
rm -rf ~/.node-gyp
npm i
```



UI sandbox
----------

1. Run Ansel:
    ```bash
    npm start
    ```

2. Run watch build (in extra console):
    ```bash
    npm run watch
    ```

3. Open the UI sandbox: `Shift`+`Ctrl`+`S` (On Mac: `Alt`+`Cmd`+`S`)

4. Change some React code and save

5. Wait for the watch build to build the changes

6. Reload UI sandbox: `Shift`+`Ctrl`+`R` (On Mac: `Cmd`+`Shift`+`R`)



Developing main thread code
---------------------------

If you change code that runs on the main thread, you have to restart Ansel each time in order to see your changes.
Here's how you can use a watch build in order to reduce turnaround time:

1. Run watch build (in extra console):
    ```bash
    npm run watch
    ```

2. Change your code.

3. Restart Ansel without building (since building is done by the watch):
    ```bash
    npm run start-no-build
    ```



CSS naming conventions
----------------------

Inspired by: [SUIT CSS naming conventions](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md)

CSS example:

```css
// Component:
// - CamelCase uppercase
.MyComponent { ... }

// Status:
// - camelCase lowercase with prefix `is` or `has`
// - Always combined with another class
.MyComponent.isExpanded { ... }

// Component children:
// - camelCase lowercase with component name plus a minus as prefix
.MyComponent-header { ... }
```

less template:

```less
// Component
.MyComponent {
    ...

    // Status
    &.isExpanded {
        ...
    }
}

// Component child
.MyComponent-header {
    ...
}
```

HTML example:

```html
<div class="MyComponent isExpanded">
    <div class="MyComponent-header">...</div>
</div>
```