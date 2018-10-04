---
description: Helper class for Twig
---

# View

## Static functions

### render

**Paramters:** \( string $template, array $context \)   
**Description:** Render Twig template with context data

```text
$viewData = [
    'headline' => 'This is a headline',
    'leadin' => 'This is a leadin',
];

View::render( '@base/page/single-article', $viewData );
```

### generate

**Paramters:** \( string $template, array $context \)   
**Description:** Generate Twig template with context data and return it

```text
$viewData = [
    'headline' => 'This is a headline',
    'leadin' => 'This is a leadin',
];

View::generate( '@base/page/partial-view', $viewData );
```

