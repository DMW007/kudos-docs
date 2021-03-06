In order to update Kudos, the Kudos.war file in the application needs to be replaced with the new version through the Web-Sphere Integrated Solutions
Console. The .war file contains all the new default data and all other application components.

### Login to the WebSphere Integrated Solution

Login to the WebSphere Integrated Solution Console for your Connections environment via a web browser.

![login](/assets/badges/update/WAS_Console_login.png)

### Replace the Kudos.war file

Navigate to Applications -> Application Types -> WebSphere enterprise applications

![was app](/assets/badges/update/was_app.png)

Select the **Kudos** application and click **Update**.

![kudos app list](/assets/badges/update/kudos_app_list.png)

Select **Replace or add a single module** option.

Type in **Kudos.war** in the text field. **Note: This is case-sensitive!**

Click Browse, navigate to and select the new **Kudos.war** file.

![select war](/assets/badges/update/select_war.png)

Follow the prompts clicking **Next**.

If prompted, click **Browse** and map the default resources as shown.

![resource mapping](/assets/badges/update/resource_mapping.png)

Follow the prompts clicking **Next**.

Click **Finish**.

Click **Save directly to master configuration**.

If the Nodes have automatically synchronized and you see this screen - Click **OK** and move to [Restart the Kudos Application](/badges/update/update_app/#restart-the-kudos-application). Otherwise continue to [Synchronize the nodes](/badges/update/update_app/#synchronize-the-nodes).

### Synchronize the nodes

To complete the update process we need to Synchronize all the nodes so that the new version of Kudos is available to them all. You can skip this Task if you have Synchronize changes with Nodes option enabled and you received a synchronization summary as shown above.

Go to System Administration > Nodes.

Select the node that Kudos is installed on. (If you are unsure you may select all the nodes)

Click on Full Resynchronize and wait for the completion message.

![full resync](/assets/badges/update/full_resync.png)

### Restart the Kudos Application

Go to Applications > WebSphere Enterprise Applications

Select the Kudos Application Checkbox.

Click Stop and wait for the Application Status column to display the Stopped icon.

Select the Kudos Application Checkbox.

Click Start and wait for the Application Status column to display the Started icon.

![stop start kudos](/assets/badges/update/stop_start_kudos.png)