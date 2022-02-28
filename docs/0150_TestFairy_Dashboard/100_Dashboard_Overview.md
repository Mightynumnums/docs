<!---![testfairy dashboard](/img/dashboard/testfairy-dashboard.gif)--->

## TestFairy Dashboard

The TestFairy dashboard is where you can view the information about your uploaded apps. The dashboard includes a list of all uploaded apps, with their own app definitions, as well as the latest sessions recorded in your account, and separate tabs for crashes, feedback, and insights.

From the dashboard you can also upload apps using the **NEW UPLOAD** button, and manage your users and account preferences.

### DASHBOARD Tab

![](/img/dashboard/dashboard-general.png)

The **DASHBOARD** tab displays information such as the number of test sessions, crashes, apps, testers, and users.

#### Apps Table
The **Apps** table lists all the apps loaded into the system.

The table displays information such as the app name and bundle ID, platform, latest version name and number, and details about the number of sessions, builds, crashes, and issues. You can also view the date the last build was uploaded, and the date the latest session was logged.

Clicking a row will open the **Builds** table (see [Builds](https://docs.testfairy.com/TestFairy_Dashboard/Builds.html) for more information).

Clicking the link button will open the app's landing page.

#### Recent Sessions
A list of the recent sessions logged in the system.

### **TESTERS** Tab

![](/img/dashboard/dashboard-testers.png)

The **TESTERS** tab displays your testers and assigned apps. See [Managing Testers](https://docs.testfairy.com/Testers/Managing_Testers.html) for more information.

### **CRASHES** Tab

![](/img/dashboard/dashboard-crashes.png)

The **CRASHES** tab displays crashes aggregated by stack trace. You can filter the list by app, version, and timeframe.
Each crash is aggregated after symbolication (if possible) and appears on a separate line. It is possible that unsymbolicated crashes will appear in separate lines, one for each crash.

### **USER FEEDBACK** Tab

![](/img/dashboard/dashboard-feedbacks.png)

The **USER FEEDBACK** tab displays user feedback submitted using the shake to report feature. The feedback is linked to the session in which it was created, and contains a screenshot, the text the user entered, and the reporter's email (which can be different from the user identified in the session).

Each issue can be linked to a bug tracking system by clicking the **CREATE BUG** button in the **ISSUE** column. Apps that are already connected to a bug tracking system will display the issue link/number inside the button. 
