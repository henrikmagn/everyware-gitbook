# Teaser templates

When an article is displayed in a board, it will use what we call a "teaser template", these templates can be added in to the clients themes and then chosen in the board settings, widget settings and more.

A teaser template is added to the theme by adding a php file in "templates/" subfolder of the theme, a comment in the php file will then set the name of the template and make it accessible in Everyboard.

 The php file will automatically get access to a php variable "$article" which is an object of type "OcArticle".

### Example of template:

{% code-tabs %}
{% code-tabs-item title="ocarticle-list.php" %}
```php
<?php
/**
 * Article Name: List element
 */

use Customer\TeaserArticle;
use EwTools\Twig\View;

$teaser = TeaserArticle::createFromOcArticle( $article );

View::render( '@base/page/partials/teaser/teaser-list-element.twig', $teaser->getViewData() );
```
{% endcode-tabs-item %}
{% endcode-tabs %}

The php file will in this example use twig for the actual HTML-rendering as follows.

{% code-tabs %}
{% code-tabs-item title="teaser-list-element.twig" %}
```php
<article class="article-teaser article-teaser--list-element">
    <div class="article-teaser__header">
        <h3 class="article-teaser__title{{ title_class ? ' '~title_class : '' }}">
                {{ title }}
        </h3>
    </div>
</article>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

