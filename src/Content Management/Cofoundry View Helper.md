﻿Cofoundry has it's own razor view helper that you can use to access Cofoundry features from any view that injects `ICofoundryHelper` or `ICofoundryHelper<TModel>`.

When injecting the helper we recommend aliasing it as `Cofoundry`, for example:

```html
@using Cofoundry.Domain

@model MyTestViewModel
@inject ICofoundryHelper<MyTestViewModel> Cofoundry


<div>
    <img src="@Cofoundry.Routing.ImageAsset(Model.HeaderImageAsset, 400, 300)">
</div>

<div>
     @Cofoundry.Sanitizer.Sanitize("<h1>My Heading</h1><script>alert('uh oh')</script>")
</div>

```

## Helpers

- **@Cofoundry.Routing:** Helpers for generating links to Cofoundry content
- **@Cofoundry.Settings:** Helper for accessing configuration settings from a view
- **@Cofoundry.CurrentUser:** Helpers for accessing information about the currently logged in user
- **@Cofoundry.StaticFiles:** Helper for resolving versioned urls to static files. [See docs](/framework/static-files)
- **@Cofoundry.Js:** Helper for working with javascript from .net code
- **@Cofoundry.Sanitizer:** Helper for sanitizing html before it output to the page. You'd typically want to use this when rendering out user inputted data which may be vulnerable to XSS attacks. [See docs](/framework/html-sanitizer)
- **@Cofoundry.Html:** Miscellaneous helper functions to make working work html views easier.