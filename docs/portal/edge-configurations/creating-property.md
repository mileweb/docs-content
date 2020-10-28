# Creating a Property

To create a property, complete the Create a Property form with required information. After creating a property, save and [validate](</docs/portal/tasks/validations.md>) the property before you deploy and test it.

## Getting Started

1. In the left pane, click **Edge Configurations**.
2. At the top right of the Properties page, click the **Create Property** button. 

<p align=center><img src="/docs/resources/images/edge-configurations/properties-create-property.png" alt="create property" width="900"></p>

3. Complete the fields in the Create a Property form. Required fields are denoted by an asterisk (\*).

<p align=center><img src="/docs/resources/images/edge-configurations/create-a-property.png" alt="edit property" width="800"></p>

| **Fields**                | **Description**                                    |
| --------------------------| ---------------------------------------------------|
| Property Name             | Enter a name that helps you identify this property.|
| Description               | Add a description to associate with this property. |
| Configuration Version     | Read-only field that shows the version number of this property. By default, your first property configuration is Version 1. |
| Description               | Add a description for this first property version. |
| Hostnames                 | Enter one or more hostnames to be accelerated and which your end users will access. |
| Origins                   | Origins are your servers that CDN360 accesses to fetch your content. You can specify more than one server. Click the **Add New** link and then see [Adding or Editing Origins in a Property](</docs/portal/edge-configurations/managing-origins.md>).|
| Edge Logic                | Write NGINX configuration code to specify how you want CDN360 to deliver content to your visitors (refer to CDNetworks' [Edge Logic documentation](</docs/edge-logic/intro.md>)). You can click the [**Wizard** button](#edge-logic-wizard) to bootstrap this configuration using the Cache Settings dialog box.|
| TLS Settings              | Select the [TLS client certificate settings](#tls-settings) for your property.|
| Real Time Logging | If this advanced feature was enabled for you, complete the [real-time logging parameters](#real-time-log). If you require this feature, contact CDNetworks.|
| Advanced Settings         | Use [advanced settings](#advanced-settings) to specify cache sharing, China ICP Beian, and a load balancer hash key.|

4. To save the property, click the **Save** button. Several basic syntax checks are performed. If errors are found, you are prompted to fix them before the property is saved. Any property version will have to be "validated" before it can be deployed to staging or production. You can click the <strong>Save & Validate</strong> button to start the validation process. When the Confirmation pop-up appears, click <strong>OK</strong>. The validation process usually takes less than a minute. You can either wait for it to finish or close the progress dialog box to perform other tasks while validation continues in the background. You can click <strong>Tasks</strong> in the left pane to [check the validation results](</docs/portal/tasks/validations.md>). If there is a failure, perform the instructions in the error message to fix it.

5. If the property is validated successfully, you can [deploy](</docs/portal/edge-configurations/deploying-property.md>) it to the staging or production environment. By default, trial users will have access to the staging environment only. Please contact the support team to enable access to the production environment.

## Edge Logic Wizard

This wizard can be used to create an initial version of the edge logic. It supports some of the most basic cache configurations. You can modify the generated edge logic code to add complicated behaviors to suit your requirements.
<p align=center><img src="/docs/resources/images/edge-configurations/property-edge-logic-wizard.png" alt="Edge Logic Wizard" width="600"></p>

## TLS Settings

This section allows you to enable HTTPS for this property by attaching a TLS certificate to it. If both RSA and ECC algorithms need to be supported, add a second certificate with an algorithm different from the first certificate. It also allows you to downgrade the protocol from HTTPS to HTTP when accessing the origin, although doing so may expose you to security risks. The remaining settings are intuitive. Specify the TLS ciphers in the format described in the [OpenSSL documentation](https://www.openssl.org/docs/man1.1.1/man1/ciphers.html).

**Note:** If you enter multiple cipher suites in the **TLS Ciphers** field, separate them with colons.


<p align=center><img src="/docs/resources/images/edge-configurations/property-tls.png" alt="TLS Settings" width="700"></p>

## Real-Time Log

If you signed an agreement with CDNetworks for accessing the real-time log, use the **Real-Time Log** section to "stream" an access log in real time to your designated HTTP or HTTPS endpoint. You can specify the format of each log entry using NGINX variables. If you use JSON format for the log, select **JSON** to escape special characters in the variable values. You can also specify a sample rate to reduce the number of log entries. Use request headers to pass additional information to the receiving endpoint.
<p align=center><img src="/docs/resources/images/edge-configurations/property-realtime-log.png" alt="Real-Time Log" width="900"></p>

## Advanced Settings

**Cache Key Hostname:** By default, the Host header value in the client request is used in the cache key. If this property contains multiple service hostnames, the contents of different hostnames will be cached separately. If you want all hostnames to share one cached copy, specify a fixed "Cache Key Hostname" to override the default behavior.

**Has ICP Beian:** If this property must be served from servers in mainland China, make sure all hostnames [have Beian on file](</docs/edge-logic/faq.md#china-delivery-and-beian>) with the Chinese government. You can then contact CDNetworks to enable this function for you. Once enabled, change the **Has ICP Beien** setting to **Yes**. 

**Note:** You can set **Has ICP Beien** to **Yes** without contacting CDNetworks; however, the functionality <ins>**WILL NOT**</ins> be enabled until you request activation from CDNetworks.

**Load Balancer Hash Key:** CDN360 uses multiple tiers of load balancing to distribute client requests to different servers, with  consistent hashing used in many of these places. By default, the URL is used as the hash key, which should be satisfactory in most cases. However, you can define additional variables to be added to the hash key to distribute the requests more evenly. One typical use case is when all requests carry the same URL, but use a particular header field to indicate different resources. In general, the variable(s) specified here should be a subset of the variables you enter [into the cache key](</docs/edge-logic/faq.md#how-do-you-include-query-parameters-andor-request-headers-in-the-cache-key>). Only the following variables are supported: `$http_*`, `$cookie_*`, `$arg_*`.

<p align=center><img src="/docs/resources/images/edge-configurations/property-advanced-settings.png" alt="Property Advanced Settings" width="700"></p>
