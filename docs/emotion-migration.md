# Emotion Migration Guide

Mineral UI was originally built on [Glamorous](https://glamorous.rocks/), a CSS-in-JS solution, that has since [been deprecated](https://github.com/paypal/glamorous/issues/419). This update necessitated a migration to another solution, [Emotion](https://emotion.sh/) being the community recommended choice.

Emotion provides a very similar API, is more performant, smaller in file size, and has an active development community.

> If you're using Glamorous outside of Mineral UI's API or experiencing other difficulties, [Glamorous's Emotion Migration Guide](https://github.com/paypal/glamorous/blob/master/other/EMOTION_MIGRATION.md) may help you.

## Mineral UI Changes

### Dependency Changes

- Remove `glamor` and `glamorous`
- Add `emotion`, `emotion-theming`, `@emotion/core` and `@emotion/styled`

### API Changes

#### `createStyledComponent`

- We've added a `withProps` option to replace the chained capability previously provided by Glamorous.

  ```js
  createStyledComponent('div', {}).withProps({ title: 'hello' });

  // should become

  createStyledComponent('div', {}, { withProps: { title: 'hello' } });
  ```

- See the [createStyledComponent API docs](https://mineral-ui.com/styling#customization-techniques-api) for further details.

#### `createThemedComponent`

- Theme may now be either an object or a function that provides an object.
- See the [createThemedComponent API docs](https://mineral-ui.com/theming#common-scenarios-api) for further details.

#### `withTheme`

- No longer takes an options argument
- See the [withTheme API docs](https://mineral-ui.com/theming#common-scenarios-api) for further details.
