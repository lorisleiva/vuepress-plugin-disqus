# Vuepress Plugin Disqus
🔌 Register a global `<Disqus />` component to add to your layouts.

This plugins is a vuepress wrapper of [vue-disqus](https://github.com/ktquez/vue-disqus).

## Installation

```bash
npm i vuepress-plugin-disqus -D
```

## Register the plugin

```js
plugins: {
    'disqus': { /* options */ }
},
```

There is only one option available: `name` which specifies the name of the disqus component. Defaults to: `Disqus`.

Note that Vuepress allows multiple syntaxes to register plugins. See [Vuepress documentation on how to use a plugin](https://vuepress.vuejs.org/plugin/using-a-plugin.html) for more information.

## Use the Disqus component

```html
<ClientOnly>
    <Disqus shortname="my-website-shortname" />
</ClientOnly>
```

It is important to wrap the `Disqus` component between the `ClientOnly` component (natively provided by vuepress) otherwise `npm run build` will fail. This is because the `Disqus` component cannot be precompiled by the server and should only live on the client side.

You can use all the props and events defined by [vue-disqus](https://github.com/ktquez/vue-disqus).

Prop            | Data Type  | required  | Description
--------------- | ---------- | --------- | -----------
`shortname`     | String     | true      | Your disqus shortname.
`title`         | String     | false     | Title that identifies the current page.
`identifier`    | String     | false     | The page's unique identifier
`sso_config`    | Object     | false     | Single sign-on (SSO)
`api_key`       | String     | false     | Your API key disqus
`remote_auth_s3`| String     | false     | implementation with Laravel/PHP
`language`      | String     | false     | Language overrides
