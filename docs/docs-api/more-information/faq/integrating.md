---
sidebar_position: -6
---

# Integrating

## Where can I find integration examples for ONLYOFFICE Docs?

The examples of integration of ONLYOFFICE Docs with your own website can be found [here](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples.md). You can choose among different web development programming languages:

- [.Net (C#) / .Net (C# MVC)](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/net-example.md)
- [Java](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/java-example.md)
- [Java Spring](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/java-spring-example.md)
- [Node.js](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/nodejs-example.md)
- [PHP](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/php-example.md)
- [PHP (Laravel)](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/php-laravel-example.md)
- [Python](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/python-example.md)
- [Ruby](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/ruby-example.md)
- [Go](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/go-example.md)
- [Java integration SDK](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/samples/language-specific-examples/java-integration-sdk.md)

The examples will show where to get the source codes, how to install and set up the working examples for integrating ONLYOFFICE Docs into your website written with the help of one of these programming languages.

If you want to connect ONLYOFFICE Docs to one of the existing document management services, you can see the ready-made connectors for the following services:

- [Alfresco](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/alfresco-integration.md)
- [Chamilo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/chamilo-integration.md)
- [Confluence](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/confluence-integration.md)
- [Drupal](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/drupal-integration.md)
- [HumHub](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/humhub-integration.md)
- [Liferay](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/liferay-integration.md)
- [Mattermost](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/mattermost-integration.md)
- [Moodle](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/moodle-integration.md)
- [Nextcloud](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/nextcloud-integration.md)
- [Nuxeo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/nuxeo-integration.md)
- [Odoo](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/odoo-integration.md)
- [ownCloud](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/owncloud-integration.md)
- [Plone](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/plone-integration.md)
- [Redmine](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/redmine-integration.md)
- [SharePoint](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/sharepoint-integration.md)
- [Strapi](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/strapi-integration.md)
- [SuiteCRM](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/suitecrm-integration.md)
- [WordPress](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/wordpress-integration.md)

Most of the connectors are available from the corresponding service application store and are easy to install. Just follow the step-by-step instructions at the [connector page](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/nextcloud-integration.md) and connect ONLYOFFICE Docs to your service.

## Which paths should I specify when integrating ONLYOFFICE Docs with my website?

After you download and unpack the examples for integration ONLYOFFICE Docs with your website, you need to open the source codes and replace all the instances of the **https\://documentserver/** string with the actual address of your installed ONLYOFFICE Docs.

## What settings should be used when connecting ONLYOFFICE to ownClowd/Nextcloud via a local and public network?

When connecting your ownCloud/Nextcloud installation to ONLYOFFICE Docs, you need to make sure that the server with ONLYOFFICE Docs installed is accessible both for the internet browsers and ownCloud/Nextcloud installations, i.e. the requests can be sent to and the responses can be accepted from the computer with ONLYOFFICE Docs installed.

The interaction scheme between ownCloud installation and ONLYOFFICE Docs is available [here](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/owncloud-integration.md#configuring-onlyoffice-app-for-owncloud). If you use Nextcloud, visit [this page](https://api.onlyoffice.com/ai-plugin-docs-update/docs/docs-api/get-started/ready-to-use-connectors/nextcloud-integration.md#configuring-onlyoffice-app-for-nextcloud) to see how you can properly set up your server.
