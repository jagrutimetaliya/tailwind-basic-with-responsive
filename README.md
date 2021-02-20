# Setting Up Tailwind CSS

### 1. Using Tailwind via CDN

Before using the CDN build, please note that many of the features that make Tailwind CSS great are not available without incorporating Tailwind into your build process.

```
 <link href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet">
 
 ```

=> You can't customize Tailwind's default theme

=> You can't use any directives like `@apply`, `@variants`, etc.

=> You can't enable additional variants like group-focus

=> You can't install third-party plugins

=> You can't tree-shake unused styles

### Example 

```
<html class="en">
<head>
    <meta charset="UTF-8"/>
    <meta name="viewport" content="width-device-width, initial-scale=1.0" /> 
    <title> Tailwind CSS Demo </title>
    <link href="https://unpkg.com/tailwindcss@^2/dist/tailwind.min.css" rel="stylesheet">

</head>
<body>
    <h1 class="text-4x1 font-bold text-center text-blue-500">Jagruti Metaliya</h1>
</body>
</html>

```
