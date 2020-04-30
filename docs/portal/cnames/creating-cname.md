# Creating a CNAME

For the CDN360 portal to serve your content, you must create a CNAME. The CNAME is configured with one or more client region rules that indicate how CDN360 will handle client requests.

Creating a CNAME is a three-step process:

- Create a CNAME using the procedure below. (Alternatively, you can use the CDN360 [API](</apidocs>).)
- [Deploy the property](</docs/portal/properties/deploying-property.md>) defined with the hostname(s) to production.

- Update your DNS records to point your hostname(s) to the CNAME.

1. In the left pane, click **CNAMEs**.
2. At the top right of the screen, click the **Create CNAME** button. 
3. Complete the fields in the Create a CNAME form. Required fields are denoted by an asterisk (\*).

![null](</docs/resources/images/cname1.png>)

| **Fields** | **Description** |
| ---------- | --------------- |
| What does a CNAME do? Add a description. | Enter a description for the CNAME. |
| CNAME | Either enter a CNAME manually in the text field or click Auto Generate to have CDN360 generate a CNAME for you. If you enter a CNAME, your typed entry must be a valid domain name. |

4. Click the **Create Client Region Rule** button. The Create Client Region Rule dialog box appears, with fields for specifying how CDN360 handles requests from different regions. Required fields are denoted by an asterisk (\*).

**Note**: If you do not create a client region rule, or if you leave the **Client Region** field empty, a rule covering ALL regions is created automatically.

a. Complete all the fields, and then click the **Create Client Region Rule** button. 

b. To specify more client region rules, repeat this step for each additional rule.

![null](</docs/resources/images/Create Client Region Rule.png>)

| **Fields** | **Description** |
| ---------- | --------------- |
| Client Region | Select a region for this rule. If you leave this field empty, a rule covering ALL regions is created automatically.|
| Client ISP | Select a client ISP.|
| Action Type | Select the type of action to be performed. Choices are:<ul><br><li>Deliver = specifies the server groups to deliver your traffic. Only one deliver action is allowed for each client region. All servers in the selected server group will be used as candidates in the load balancing algorithm.<li>Redirect = directs traffic requests to the target specified in the Redirect target field (see below). This can be your origin site or another CDN provider. There can be multiple redirect actions for each client region.<li>Reject = directs traffic requests to web servers that always respond with a 403 - forbidden error message. Only one reject action is allowed for each client region.|
| Server Group | If Action Type is set to Deliver, select one or more server group options:<br><li>Standard = standard server group.</li><li>Premium = includes the standard server group.<li>Premium+ = includes the standard and premium server groups.<li>Ultra = includes the standard, premium, and premium+ server groups.|
| Redirect Target | If Action Type is set to Redirect, specify an IP address or hostname to which CDN360 will redirect your traffic..|
| Weight | Adjust how this rule behaves relative to other rules for the same client region.|


5. Expand **Advanced Settings**, and then confirm or change the following field.

![null](</docs/resources/images/cname3.png>)

| **Fields**      | **Description** |
| --------------- | --------------- |
| Has Beian       |        Select whether content will be served from PoPs inside or outside China. Choices are: <ul><br><li>No = content is served to website visitors in China from PoPs located outside China. (*default*)<li>Yes = content is served to website visitors in China from PoPs located in China.    |

1. Click the **Create CNAME** button.
2. After creating the CNAME, update your DNS records to point your hostname(s) to the CNAME.