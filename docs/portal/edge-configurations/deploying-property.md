# Deploying Your Property

After you create and validate a property version, you are ready to deploy it. Initially, we highly recommend that you always deploy the property to the staging environment to make sure the property is configured properly and behaves as expected. After you confirm that the property is ready to go live, you can deploy it to the production environment.

1. In the left pane, click **Edge Configurations**. 

2. On the Properties page, click the ID of the property you want to deploy. 

3. Scroll down to the **Deployment** section, select either **Staging** or **Production** from the **Deployment Destination** drop-down list, and then click the **Deploy Configuration** button.

**Note:** To view the deployment history of the property before deploying it, click the **Deployment History** button.

<p align=center><img src="/docs/resources/images/edge-configurations/property-deployment.png" alt="deployment selections and button" width="900"></p>

4. If the property is already deployed to the selected environment, the next form compares the deployed version with the one you want to deploy. If you are satisfied with the differences, click the **Deploy to ...** button on the top right corner (or click **Back** to cancel the deployment).

5. When the Deployment Confirmation pop-up appears, click **OK**. Usually, the deployment process finishes in 5 minutes. You can either wait with the progress dialog box, or close it to perform other tasks while the deployment continues in the background. You can click **Tasks** in the left pane to check the status of the deployment at any time.

6. Click [here](</docs/portal/edge-configurations/testing-property.md#testing-property-in-staging>) for instructions about testing the property in the staging environment.

# Undeploying a Property

1. In the **Actions** column on the Properties page, click the vertical ellipsis of the deployed property you want to undeploy, and then select **Undeploy from Staging** or **Undeploy from Production**.

<p align="center"><img src="/docs/resources/images/edge-configurations/property-actions-undeploy.png" alt="property undeployment" width="900"></p>

2. When the Undeployment Confirmation pop-up appears, click **Yes, Undeploy!** You can either wait with the progress dialog box, or close it to perform other tasks while the undeployment continues in the background. You can click **Tasks** in the left pane to check the status of the undeployment at any time.

# Viewing a Property's Deployment History

In the **Actions** column on the Properties page, click the vertical ellipsis of the property whose deployment history you want to view, and then select **Deployment History**. The Deployment page appears, with a deployment history of the selected property.
