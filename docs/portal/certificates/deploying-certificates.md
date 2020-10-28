# Deploying and Undeploying Certificates

After you create or update a certificate, you must deploy it to either the staging or production environment before it can be used by any properties. If a certificate is no longer used by any property in those environments, you should undeploy it. Undeploying a certificate is also a prerequisite if you want to delete a certificate from the CDN360 platform.

**Note**: To deploy a certificate to, or undeploy a certificate from, the staging or production environment, you must be the owner of the certificate.

## Deploying a Certificate

1. In the left pane, click **Certificates**. 
2. On the Certificates page, click the name of the certificate you want to deploy.
3. Scroll down to the **Deployment** section, and then select **Staging** or **Production** from the **Deployment Destination** drop-down list.
<p align="center"><img src="/docs/resources/images/certificates/certificate-deployment-options.png" alt="Deployment Options" width="700"></p>

<strong>Note:</strong> To view the deployment history of the certificate before deploying it, click the **Deployment History** button.

4. Click the **Deploy Configuration** button. When the confirmation pop-up appears, click **OK**. The deployment process takes about 5 minutes. You can watch the progress and wait for it to finish, click the **Go to Dashboard** button in the pop-up to go to the Dashboard, or close the pop-up to perform other tasks while deployment continues in the background. You can always click **Tasks** in the left pane to check the status of the deployment.

## Undeploying a Certificate

If you no longer need a certificate in a staging or production environment, you can undeploy the certificate.

1. In the left pane, click **Certificates**.
2. In the **Actions** column on the Certificates page, click the vertical ellipsis of the certificate you want to undeploy, and then select **Undeploy from Staging** or **Undeploy from Production**.
<p align="center"><img src="/docs/resources/images/certificates/certificate-actions.png" alt="Certificate Actions" width="900"></p>

3. When the confirmation pop-up appears, click <strong>OK</strong>. The undeployment process takes about 5 minutes.
