## Principles
- Design for the user experience.
- Implement for mobile first.
- Assure responsiveness.
- Guarantee ease of maintenance.
- **D**on't **R**epeat **Y**ourself.
- **K**eep **I**t **S**emantic **S**assy.
- Guarantee accessibility.
- Deliver browser compatibility.

## Process
1. Review full design.
2. Extract possible variables (eg. colors, spacing, etc).
3. Customize Bootstrap's variables (eg. typography, link, buttons, etc).
4. Provide images.
5. Define general mixins, functions, helpers & placeholders.
6. Configure base template.
7. Implement different sections.
8. Test responsiveness, compatibility and performance.

## HTML
- Use HTML5 semantically.
- Use single containers for each block.
- Define a base template.
- Make use of reusable partials.
- Bundle files to avoid too many HTTP requests.
- Avoid inline CSS/JS, keep HTML clean.
- Maintain HTML loosely coupled from the framework.
- Design for accessibility (`aria`, `role`, `alt`, etc).
- Don't leave content without tags.
- Explain which div you're closing, when you have 4+ nesting levels.

## Sass
- Follow [Frontend Boilerplate](https://github.com/vintasoftware/frontend-boilerplate) about which partial file new code goes on.
- Use a temporary `shame.scss` file for all last minute hacky code.
- Componentize to decouple.
- Don't try to mock the HTML.
- Naming conventions: lowercase, hyphen-separated.
- Prefer `.class` over `#id`.
- Name selectors according to functionality, not presentation.
- Use CSS semantically (Example `input[attribute]`...).
- Define clear naming convention for parent-child relationships (eg. parent `.post` with children `.post-title` and `.post-description`).
- Respect Inception Rule: don’t go more than four levels deep.
- Keep this order: `@extend`, `@include`, styling, nested-styling.
- Define variables for all customizable values (ex: colors, typography, base spacing, sizes).
- Never use `!important` unless you're overriding a non-customizable (via variables) framework.
- Use appropriate images for each device.
- Use CSS3 instead of images, when possible.
- Comment large blocks.
- Prefer CSS shorthands (`padding`, `margin`...).
- Prefer `rem` vs `em` for scalability.
- Use `px` only for fixed values that are not responsive.
- Prefer fonts from [Google Fonts](https://fonts.google.com/?authuser=0) they might be already cached in the browser.
- Define  consistent type scale and avoid overriding it.
- Limit use of floats within components and elements to avoid nested floating.
- Use plural noun to define the container of singular modules (eg. `ul.tags`, `li.tag`).
- Use adjectives to semantically denote subclasses (eg. `.submit-button`).
