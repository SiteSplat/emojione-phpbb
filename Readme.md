#Emoji One for phpBB 3

![Preview](preview.png)

This repository provides a full installation of [Emoji One](http://emojione.com/), a complete open source emoji set, to replace phpBB 3.x default smilies. It includes **1 625** smilies and **2 172** shortcuts.

## Installation

1. [Download](https://github.com/sylvaindurand/emojione-phpbb/archive/master.zip) and extract the package.
2. Put `emojione` folder and `emojione.pak` file into phpBB' `/images/smilies/` folder.
3. Change `SMILEY_LIMIT` to `3000` in `includes/constants.php`
4. In phpBB administration panel, go to `Posting` tab, then to `Smilies` section, and select `Install smilies package`.

## Extend to Emoji
Since version 3.2, phpBB automatically converts emojis to images, but from a different provider.

To change it, edit `/vendor/s9e/text-formatter/src/Plugins/Emoji/Configurator.php` and change the line:

```php
return $template;
```

With:

```php
return '<img alt="{.}" class="smilies" src="./images/smilies/emojione/' . '{@seq}.' . 'svg" />';
```


## Troubleshooting

If you get an error message like `Fatal error: Allowed memory size of x bytes exhausted (tried to allocate x bytes)`, modify your `php.ini` configuration file and try to increase `max_input_time`, `memory_limit` and ` max_execution_time` variables.


## License

[Emoji One](http://emojione.com/) artworks are published under License [Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/).

The python code is written by Sylvain Durand and released under [License MIT](http://opensource.org/licenses/MIT).
