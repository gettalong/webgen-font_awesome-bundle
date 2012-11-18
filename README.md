# Font Awesome icon font for webgen

This is a [webgen] extension bundle that provides the [Font Awesome][1]
icon font. This icon font can be used stand-alone or combined with the
[webgen Twitter Bootstrap bundle][2].

[webgen]: http://webgen.rubyforge.org
[1]: http://fortawesome.github.com/Font-Awesome/
[2]: https://github.com/gettalong/webgen-sass_twitter_bootstrap-bundle#readme


# Usage

The bundle uses [Sass] for providing the necessary CSS files and for
compatibility to [webgen Twitter Bootstrap bundle][2], so be sure you
have Sass installed.

* If you want to use the font without the Twitter Bootstrap framework,
  just import the stylesheet in one of your Sass files:

      @import "/font-awesome";

* If you want to use the font with the Twitter Bootstrap framework, ie.
  instead of the Glyphicons, you need to load this bundle after the
  Twitter Bootstrap bundle!

  Then just load the Bootstrap framework as usual with

      @import "/bootstrap/bootstrap";

  If you don't use this approach because you selectively load parts of
  the Bootstrap framework, make sure that you import `/font-awesome`
  instead of `/bootstrap/sprites`!

[Sass]: http://sass-lang.com/


# Installation

The easiest way to install this extension bundle is by installing the
corresponding Rubygem:

    gem install webgen-font_awesome-bundle

If you don't use Rubygems, copy the folder
`lib/webgen/bundle/font_awesome` into your `ext` directory.

After that you just need to tell webgen to use this extension bundle by
adding the following line to your `ext/init.rb` file:

    load("font_awesome")

Don't forget to add this line after the line for the Twitter Bootstrap
bundle so that everything works out of the box!


# Copyright and license

Copyright 2012 Thomas Leitner

Licensed under the Apache License, Version 2.0 (the "License"); you may
not use this file except in compliance with the License. You may obtain
a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

* * *

The used files from the Font-Awesome repository are licensed under the
CC-BY 3.0 license (see
<https://github.com/FortAwesome/Font-Awesome#license>).
