# Get started

**ONLYOFFICE Apps Plugins SDK** allows developers to create their own plugins and add them to the ONLYOFFICE Apps portal.

This documentation describes:

- How to [create](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/creating-plugin-template.md), [code](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin.md), [style](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/styling-plugin.md), [build](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/building-plugin.md), and [upload](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/adding-plugin.md) a plugin
- What [plugin types](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins.md) and [items](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items.md) are available
- What the [plugin structure](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/plugin-structure.md) consists of
- How to use plugin variables, methods, [messages](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/utils.md), and [events](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/enums/Actions.md)
- What [plugin components](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components.md) can be used to build a plugin

## What plugins can do

Here are some examples of what you can do with ONLYOFFICE Apps plugins:

- connect third-party services, like [Draw.io](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/samples/ready-to-use-samples/drawio.md), [Markdown](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/samples/ready-to-use-samples/markdown.md), [Speech to Text](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/samples/ready-to-use-samples/speech-to-text.md), etc.
- enhance the existing user experience and the editors' functionality: [PDF converter](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/samples/ready-to-use-samples/pdf-converter.md).

Code samples are available at [GitHub](https://github.com/ONLYOFFICE/docspace-plugins).

## How to create plugins

To create your own plugin, you need to follow a few steps:

1. Preparing
2. Creating plugin template
3. Coding
4. Building
5. Uploading to the portal

### Step 1. Preparing

[Prepare](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/preparing.md) your environment: make sure you have access to ONLYOFFICE Apps (either the on-premises version or an ONLYOFFICE Apps SaaS account), then install the *@onlyoffice/docspace-plugin-sdk* npm package globally:

``` sh
npm i -g @onlyoffice/docspace-plugin-sdk
```

Now, the **npx** command is available, which will be used to create a plugin.

### Step 2. Creating plugin template

1. To create a plugin template, run the following command:

   ``` sh
   npx create-docspace-plugin
   ```

2. Configure the plugin in the terminal by specifying the plugin settings in the dialog, such as name, version, author, logo, etc.

3. Select the plugin scopes from the list: use the arrow keys to navigate and press *Space* to select the necessary scopes (API, Settings, Context menu, etc.).

For more information about plugin settings and scopes, see [creating a plugin template](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/creating-plugin-template.md).

![Creating template](https://api.onlyoffice.com/assets/images/docspace/creating-template.png#gh-light-mode-only)![Creating template](https://api.onlyoffice.com/assets/images/docspace/creating-template.dark.png#gh-dark-mode-only)

### Step 3. Coding

Develop a plugin. Follow the plugin structure described [here](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/plugin-structure.md).

- Write code for each [plugin type](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins.md) using the corresponding variables, methods and [items](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/items.md). Put the scripts into the *src* folder. Specify the required [Plugin](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/plugins/IPlugin.md) interface for each plugin to be embedded in the portal.

  ![Plugin structure](https://api.onlyoffice.com/assets/images/docspace/plugin-structure.png#gh-light-mode-only)![Plugin structure](https://api.onlyoffice.com/assets/images/docspace/plugin-structure.dark.png#gh-dark-mode-only)

- Specify [plugin messages](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/utils.md) that will be returned by the items. Use the appropriate [events](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/enums/Actions.md) that will be processed on the portal side.

- Learn which [plugin components](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/coding-plugin/interfaces/components.md) can be used for the ONLYOFFICE Apps plugin interface and add them to your scripts.

Code samples are available at [GitHub](https://github.com/ONLYOFFICE/docspace-plugins).

### Step 4. Building

To build a plugin, you need to have *npm* (included with Node.js) installed. The plugin template builds with Vite 8, which requires Node.js `^20.19.0 || >=22.12.0`.

1. Install all the necessary dependencies using the **npm install** command in the plugin root folder (if this was not done previously in Step 2).

2. Build a plugin archive by running the **npm run build** command. The completed plugin will be located in the *dist* folder and can be uploaded to the ONLYOFFICE Apps portal. For more information, see [building a plugin](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/building-plugin.md).

### Step 5. Uploading to the portal

To upload a plugin to the ONLYOFFICE Apps portal, follow the instructions [here](https://api.onlyoffice.com/ai-plugin-docs-update/docspace/plugins-sdk/usage-sdk/adding-plugin.md).

The plugin will appear in the plugin list and start functioning automatically.
