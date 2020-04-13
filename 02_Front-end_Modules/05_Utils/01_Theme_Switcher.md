# Theme Switcher

This utility is used to dynamically switch light dark themes

**Methods:**

- **setTheme** - sets theme by its _name_
- **toggle** - toggles current theme by another
- **setDark** - sets dark theme
- **setLight** - sets light theme

## setTheme()

```js
import switcher from "@/utils/theme-switcher";

switcher.setTheme("light"); // sets light theme
switcher.setTheme("dark"); // sets dark theme
switcher.setTheme("some-error-string"); // sets light theme (as default)
```

## toggle()

```js
// light theme was on
import switcher from "@/utils/theme-switcher";

switcher.toggle(); // changed to dark
switcher.toggle(); // changed back to light
```

## setDark()

```js
import switcher from "@/utils/theme-switcher";

switcher.setDark(); // theme changed to dark
```

## setLight()

```js
import switcher from "@/utils/theme-switcher";

switcher.setLight(); // theme changed to light
```
