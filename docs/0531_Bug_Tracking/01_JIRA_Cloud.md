# Connect TestFairy to JIRA Cloud

## 1. Create a JIRA API token

1.1 log in to [https://id.atlassian.com/manage/api-tokens#](https://id.atlassian.com/manage/api-tokens#) and click on "Create API token"

![Create JIRA API](/img/bug-tracking/jira-create-api.png)

1.2 Label the new token "TestFairy".

![Set TEstFairy JIRA Key](/img/bug-tracking/jira-label.png)

1.3 Copy the API Token.

![Copy token](/img/bug-tracking/jira-token.png)

## 2. Configure JIRA in your TestFairy settings: 

2.1. Open your TestFairy account Preferences 

![Open TestFairy preferences](/img/bug-tracking/jira-cloud-1.png)

2.2 Choose "Bug Systems" -> "JIRA", and enter your JIRA Username, API Token and JIRA URL. 

![Configure JIRA cloud](/img/bug-tracking/jira-cloud-2.png)


## 3. (optional) Install the TestFairy Chrome Extension

The TestFairy Chrome Extension is available [here](https://chrome.google.com/webstore/detail/testfairy-for-jira/joaafaemekbkgekhjbaldlllcnjifcee). With this Chrome extension, every JIRA issue that has a link to a TestFairy session will contain the right TestFairy session, timeline, logs, and crash reports enbedded in the JIRA issue.

## 4. (optional, if you didn't install the Chrome extension) Add The TestFairy JIRA Add-on to your JIRA account

The TestFairy JIRA Add-on adds TestFairy videos to JIRA issues.

In order to install it please follow these steps:

4.1. Open JIRA Settings

![JIRA-settings](/img/bug-tracking/jira-settings.png)

4.2 Open Apps

![JIRA-settings](/img/bug-tracking/jira-settings1.png)

4.3 In the Apps manu press 'Find new apps'

![JIRA-apps](/img/bug-tracking/jira-find-apps.png)

4.4 Add "TestFairy for Jira" to your account.

![JIRA-testfairy app](/img/bug-tracking/jira-discover.png)

4.5 On the first issue that is created, click on the "3 dots" icon and choose "TestFairy Session"

![JIRA-testfairy app](/img/bug-tracking/jira-3-dots.png)


## This is how JIRA issues look After the installation

![JIRA-setup](/img/bug-tracking/hira6a.png)
![JIRA-setup](/img/bug-tracking/jira5b.png)
![JIRA-setup](/img/bug-tracking/jira6c.png)

## 5. (optional ,highly recommended) Map JIRA Custom Fields.

The TEstFairy JIRA integration allows you to automatically populate any field in JIRA when creating a new issue.
You can do that with standard TestFairy data like app name, version, user, device etc. or with your own seesion attributes, any key and value you push to our SDK in real time.
In order to map [follow these steps](How_To_Map_JIRA_Custom_Fields.html)
