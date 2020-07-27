# README

## what's this?

This is my current VSCode theme named **Cobalt Elf**. It contains two different color themes and one icon theme. It's not published to marketplace and I'll explain why.

I've tried several different themes from the marketplace and let's just say, I like one theme very much but I have some ideas about syntax highlighting or, I like the syntax highlighting rules from theme A but UI colors from theme B. What should I do?

Well, there is a way to achieve this just in your VSCode's setting file. In `%APPDATA%\Code\User\settings.json` if you are on Windows, you can modify theme colors like this,

```json
"workbench.colorCustomizations": {
  "[Theme Name]": {
    "scrollbarSlider.background": "#355166cc",
    "scrollbarSlider.background": "#2f3336cc"
  }
},
```

And for syntax highlighting rules,

```json
"editor.tokenColorCustomizations": {
"[Theme Name]": {
    "textMateRules": [
      {
      "name": "Comment",
      "scope": ["comment", "punctuation.definition.comment"], // these are called textMate rules, I suppose?
      "settings": {
        "fontStyle": "italic",
        "foreground": "#0088ff"
        }
      },
    ]
  }
}
```

At first, I add all my settings in my local VSCode settings, but sooner or later, it's like I added maybe hundreds line of code just for colors, and those settings are not really related to how you write code or telling VSCode what it should do to be _smarter_, it's just about colors and font styles. And it's a bit hard to track and update.

So I made this, it's more like a combination instead of a brand new theme with my own flavor to those themes I've used before. That's the reason I'm not going to publish it (at least for now). 😯

## what exactly I've done?

There are two color themes, one is called **Cobalt Night Elf**, the other is **Cobalt Dark Elf**.

The syntax highlighting are mainly from [Cobalt2 Theme Official](https://marketplace.visualstudio.com/items?itemName=wesbos.theme-cobalt2) but I changed a little bit, mostly for `TypeScript` and `CSS`. Basically **Cobalt Night Elf** is the same as [Cobalt2 Theme Official](https://marketplace.visualstudio.com/items?itemName=wesbos.theme-cobalt2) with a slightly different syntax highlighting.

**Cobalt Dark Elf** has the same syntax ing colors but with dark background. I've always want to use a black and orange theme and I found this [Horizon Theme](https://marketplace.visualstudio.com/items?itemName=jolaleye.horizon-theme-vscode). It looks really good but I prefer orange than pink. So the UI colors are from it.

There's also a icon theme from [Monokai Pro](https://marketplace.visualstudio.com/items?itemName=monokai.theme-monokai-pro-vscode), you can find it by choosing `File -> Preference -> File Icon Theme -> Cobalt Elf`.

**Notice**: [Monokai Pro](https://marketplace.visualstudio.com/items?itemName=monokai.theme-monokai-pro-vscode) is not a free theme although you can use it without a license. If you really like it, please buy a license and support their work.

These themes are really fantastic, choose what you want!

## how to use

Clone this repo to `~/.vscode/extensions` or `C:\Users\<your name>\.vscode\extensions` and you are good to go.

## maybe more?

I'd like to talk something more about syntax highlighting here. If you open a theme extension, or for example, in this repo's theme folder, there are two `.json` files, choose one and you will find something like this,

```json
"tokenColors": [
  {
    "name": "Comment",
    "scope": ["comment", "punctuation.definition.comment"],
    "settings": {
      "fontStyle": "italic",
      "foreground": "#0088ff"
    }
  }
]
```

Here it seems like to say, I want my comment to be this kind of color and italic, but how? What exactly are `"comment"` and `"punctuation.definition.comment"`, where does it come from? How about numbers or variables?

These things are called `textMate` scopes, it's kind of a specification to define which part belongs to what exactly thing in a language. I didn't find an official documentation of them, maybe it just don't exist. But don't worry, you don't need to become a language master to use them.

In VSCode, there is a really useful trick to help you understand and use these scopes, press `F1` or `ctrl+shift+p`, choose `Developer: Inspect Editor Tokens and Scopes`, it will show all the information with foreground color, background color, textMate scopes and other infos at what your cursor currently is (if it's in the editor).

So if you really want to know how to make variables or entitys or brackets or everything else to a different color, just inspect them and add your own rules.

## todo

Add images.

Add more icons. It's available to use icons with `.svg` files or `.woff` files. Here they're all defined in one `.woff` file. For now, I'm using [FontForge](https://fontforge.org/en-US/) to edit fonts, I'm still learning to use it. Hopefully I will add more icons.

## links

[Learn how to make a VSCode color theme](https://code.visualstudio.com/api/extension-guides/color-theme)

[Learn how to make a VSCode file icon theme](https://code.visualstudio.com/api/extension-guides/file-icon-theme)

[Learn more about VSCode color formats](https://code.visualstudio.com/api/references/theme-color#color-formats)

[Learn more about textMate scopes](https://macromates.com/manual/en/language_grammars#naming_conventions) and [this](https://www.sublimetext.com/docs/3/scope_naming.html)

[FontForge](https://fontforge.org/en-US/)
