# ViewportSize

Linearly scale length from a minimum number at a smaller viewport to a maximum at a larger viewport.

## How to Use

1. Import `_viewportsize.scss` in your sass file
   ```
   @import "viewportsize";
   ```
2. Now you can use the `vs` mixin like this
   ```
   @include vs($min-viewport-width, $min-size, $max-viewport-width, $max-size, $property: "font-size");
   ```

## Example

1.  ```
    h1 {
        @include vs(320px, 32px, 960px, 48px);
    }
    ```
    
    This will compiled to

    ```css
    h1 {
        font-size: 32px;
    }

    @media screen and (min-width: 320px) {
        h1 {
            font-size: calc(3.75vw + 12px);
        }
    }

    @media screen and (min-width: 960px) {
        h1 {
            font-size: 48px;
        }
    }
    ```

2.  ```
    .container {
        @include vs(320px, 16px, 960px, 24px, padding);
    }
    ```
    
    This will compiled to

    ```css
    .container {
        padding: 16px;
    }

    @media screen and (min-width: 320px) {
        .container {
            padding: calc(1.25vw + 12px);
        }
    }

    @media screen and (min-width: 960px) {
        .container {
            padding: 24px;
        }
    }
    ```

## License

MIT