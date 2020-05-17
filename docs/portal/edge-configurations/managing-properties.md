# Configure the Edge with Properties

A "property" is the configuration of one or more hostnames (domains) that need to be deployed to the CDN360 edge servers. It determines how you want the servers to obtain, cache, modify, and distribute your content to the end users. The key elements of a property include:
- Hostname(s) to be accelerated.
- One or more origin servers.
- Caching rules for different types of contents.
- Modifications to the URL or HTTP header fields.
- Whether HTTPS is required, TLS certificates, and TLS protocol version.

## Managing Properties

On the CDN360 platform, property configurations are versioned to support tracking the history of changes and allow rollback if needed. Each version can be  deployed independently to the staging or production environment. On the portal, you can create, modify, validate, and deploy properties. You can also undeploy and delete properties if needed.

Properties are managed from the Properties page. To display this page, click **Properties** in the left pane. The following figure shows the key elements on the page, and the table following the figure describes them.

<p align=center><img src="/docs/resources/images/Properties Page.png" alt="properties page" width="900"></p>


| **Fields**   | **Description**                                                                           |
| :----------: | ----------------------------------------------------------------------------------------- |
| 1            | A search box that you can enter any keyword to filter the property list.                  |
| 2            | The list of all properties that are available to you.                                     |
| 3            | Dropdown list to take actions on each property.                                           |
| 4            | The button to [create new properties](</docs/portal/edge-configurations/creating-property.md>).    |

## Property Actions
Clicking the **Actions** drop-down list shows all the available actions that can be performed with properties.
(Show Properties Actions drop-down menu??)
- **Edit**: [Update](</docs/portal/edge-configurations/editing-properties.md>) the selected property.
- **Compare**: [Compare](</docs/portal/edge-configurations/comparing-properties.md>) two properties.
- **Undeploy**: Undeploy a property from the staging or production environment.
- **Delete**: Delete the property.
