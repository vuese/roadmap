# Vuese2.x Roadmap

**Tips: Version 2.0 will be fully compatible with 1.0.**

In the 2.x version, `vuese` will be managed as [monorepo](https://github.com/babel/babel/blob/master/doc/design/monorepo.md). Currently developed on the monorepo branch: [https://github.com/vuese/vuese/tree/monorepo](https://github.com/vuese/vuese/tree/monorepo)

## @vuese/cli

**The goal is to provide simple and fast document generation for any project**

- Generate a [docute](https://github.com/leptosia/docute) document
- Generate markdown files to the specified directory.
- Generate the markdown file in the same component folder. (Related: [#17](https://github.com/vuese/vuese/issues/17))
- Easily preview components as documents
- Incremental update
- Integrate existing document systems

## @vuese/parser

**Core vue file parsing module, you can use it to do any more advanced things**

If something is missing here, thanks for submitting PR:

- Full feature support and plugin architecture
  - Object-based component
  - Class-based component
  - jsx / tsx
  - slots
    - Slots(scoped) in the template
    - `this.$slots.xxx`
    - `this.$scopedSlots.xxx()`
    - `context.$slots().xxx` - For functional components
    - `context.children` - For functional components
  - events
    - `$emit` in the template
    - `this.$emit()`
    - `.sync` event - `this.$emit('update:some-prop', 1)`
    - `v-model` event - Similar to `.sync`
  - methods
    - All forms of methods
  - props
    - All forms of props
  - name
    - Component name
  - componentDesc
    - Description of the component

## @vuese/markdown-render

**Generate a markdown string based on the result of @vuese/parser**

Essentially, this is an example of using parsing results, but you can use it easily, and don't forget that we might be able to do more with the @vuese/parser module.

## @vuese/loader & @vuese/webpack-plugin

`@vuese/cli` is a tool for quickly creating document prototypes that don't have a more flexible documentation solution. So this is why `@vuese/loader` and `@vuese/webpack-plugin` are needed.

Our goal is to focus only on the parts that can be automated, and does not limit how your document project is organized and what document framework is used. Of course, we can also provide fast solutions.

### @vuese/loader

**A webpack loader**

[TODO]

### @vuese/webpack-plugin

**A webpack plugin**

[TODO]

## vuese-explorer

**`@vuese/parser` and `@vuese/markdown-render`'s playground.**

The goal is:

- For a quick experience
- For convenient use of the `@vuese/parser` module for underlying development
- For quickly reproduce the bug

What needs to be done is:

- More convenient to view the analysis results of various features
  - Need a selection button, options include: `jsx`, `Object-based`, `class-based`, etc.

## Independent document project

Document site