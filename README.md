# 🌈 nvim-ts-rainbow 🌈
Rainbow parentheses for neovim using tree-sitter.
This is a module for [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter), not a standalone plugin. It requires and is configured via nvim-treesitter

Should work with any language supported by nvim-treesitter. If any language is missing, please open an issue/PR.


## Installation and setup
Install and set up nvim-treesitter according to their documentation. Install this plugin, then add a `rainbow` section in the [call to `require("nvim-treesitter.configs").setup()`](https://github.com/nvim-treesitter/nvim-treesitter#modules):
```lua
require("nvim-treesitter.configs").setup {
  highlight = {
      -- ...
  },
  -- ...
  rainbow = {
    enable = true,
    -- disable = { "jsx", "cpp" }, list of languages you want to disable the plugin for
    extended_mode = true, -- Also highlight non-bracket delimiters like html tags, boolean or table: lang -> boolean
    max_file_lines = nil, -- Do not enable for files with more than n lines, int
    -- colors = {}, -- table of hex strings
    -- termcolors = {} -- table of colour name strings
  }
}
```

If you want to enable it only for some filetypes and disable it for everything else, see https://github.com/p00f/nvim-ts-rainbow/issues/30#issuecomment-850991264

### Colours
I've used the gruvbox palette because it is nice and subtle. I wanted to use VIBGYOR for an actual rainbow, but
 - indigo and blue look the same.
 - the colours were too bright and distracting.

To change the colours you can set them in the setup:
```lua
require'nvim-treesitter.configs'.setup{
  rainbow = {
    -- Setting colors
    colors = {
      -- Colors here
    },
    -- Term colors
    termcolors = {
      -- Term colors here
    }
  },
}
```

If you want to override some colours (you can only change colours 1 through 7 this way), you can do it in your init.vim: (thanks @delphinus !). You can also use this while writing a colorscheme
```vim
hi rainbowcol1 guifg=#123456
```
## Screenshots
 - Java

![alt text](https://raw.githubusercontent.com/p00f/nvim-ts-rainbow/master/screenshots/java.png)

The screenshots below use a different colorscheme
 - Fennel:

![alt text](https://raw.githubusercontent.com/p00f/nvim-ts-rainbow/master/screenshots/fnlwezterm.png)
![alt text](https://raw.githubusercontent.com/p00f/nvim-ts-rainbow/master/screenshots/fnltreesitter.png)
 - C++:

![alt text](https://raw.githubusercontent.com/p00f/nvim-ts-rainbow/master/screenshots/cpp.png)
 - Latex (with tag begin-end matching)

![alt text](https://raw.githubusercontent.com/p00f/nvim-ts-rainbow/master/screenshots/latex_.png)
## Credits
Huge thanks to @vigoux, @theHamsta, @sogaiu, @bfredl and @sunjon and @steelsojka for all their help
