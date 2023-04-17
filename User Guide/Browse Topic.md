
# Browse topics

The **Browse topics** page displays the latest topics and available topics in cards containing the topic related information. 

Each topic in the card is classified as:

  

- ![Image not Available](/assets/icon1.png) - Refers to unclassified information disclosed to the public in the normal course of duty

- ![Image not Available](/assets/icon2.png) - Refers to unclassified information not disclosed to the public in the normal course of duty

- ![Image not Available](/assets/icon3.png) - Refers to unauthorised disclosure could cause SOME DAMAGE to an Agency

Published date for each topic in the card is displayed. 

Mouse hover over icons and a tooltip appears for each topic in the card: 

- ![Image not Available](/assets/icon4.png) – This icon displays “Approval is needed from publisher before you subscribe” 

- Visibility icon – Displays who can view the topic: 

  - ![Image not Available](/assets/icon13.png) - This icon displays "Anyone can view this topic"
  - ![Image not Available](/assets/icon5.png) – This icon displays "All government agencies can view topic"
  - ![Image not Available](/assets/icon6.png) – This icon displays "Only members of my agency can view topic" 
  - ![Image not Available](/assets/icon12.png)- This icon displays "Only members of the team can view this topic"
  - ![Image not Available](/assets/icon11.png)- This icon displays "Only you can view this topic"

  
 ![Image not Available](/assets/Fig1.png)   

You can search for topic by entering the topic name in the ![Image not Available](/assets/icon7.png) input box. 

Click ![Image not Available](/assets/icon8.png) to filter the following:

- **Show only my topics** - Filter your own created topics
- **Classification** – Filter the topic classified as Official-Open, Official-Closed, and Restricted
- **Approval** – Filter the topic whether approval is needed from the publisher as Free access or Request needed
- **Publish date range** – Filter the topic based on selected range by published date
- **Visibility** - Select any one visibility from the drop down list for Public, All government agencies, Only my agency, Only my team and Only me
- **Tags** - Filter the keywords used to organise and categorise the topics
- **Organisation** – Select from the dropdown to filter the organisation
- **Sort by** – Select from the dropdown to filter the newest, oldest, and recently updated topics

- Alternatively, you can click **Clear all filters** to reset the filters

![Image not Available](/assets/Fig29a.png)

In the **Browse topics**, you can start to create your own topic and project by clicking **Create** button. 

- For related information about how to **Create topic**, see **[My topics](/User%20Guide/Projects?id=my-topics)**

- For related information about how to **Create project**, see **[Projects](/User%20Guide/Projects)**


## Topic details

You can view each topic in the card to know the details and what the topic is all about.

As a **Publisher** you can view 3 tabs as follows:

- Overview
- Subscribers 
- Adaptor

**Overview** 

In this tab you can **view the topic details** and can do the following: 

- See the topic overview - topic path, topic description, view payload, project name
- See folders and its subfolders within the topic
- Edit folders and its subfolders within the topic
- Subscribe to the topic
- See the status of the topic
- Edit own topic only
- View payload - Payload last seen time and can copy large payload to clipboard

![Image not Available](/assets/Fig30.png)

**Publisher to view payload from portal**

Publisher can **View Payload** after they published via MQTT Client by downlaoding the SSL certs from the Projects page.

**Step 1** Navigate to **Browse topics**.

**Step 2:** On click a topic that you have published via MQTT Client and the **Topic details** page displayed.

**Step 3:** Click **View Paylaod** button.

**Step 4:** In Paylaod preview pop-up, click **Show paylaod** button.
  
![Image not Available](/assets/Fig105_12.png)

**Note:** Payload preview supports JSON, XML, and text formats

**Step 5:** Hover the **last seen 1 day ago** as shown in the below screenshot, user can see **Payload last seen time**.

![Image not Available](/assets/Fig105_11.png)

**Step 6:** Click the **copy tooltip icon** in the payload preview, user can copy the paylaod into clipboard

![Image not Available](/assets/Fig105_10.png)
  
**Note:** *User can copy large payload to clipboard*

![Image not Available](/assets/Fig105_13.png)
   
- Create new child topics from the folder
- **Suspend** topic
- **Delete** own topic only

For related information about how to **Create child topic**, **Suspend topic**, see **[Projects](/User%20Guide/Projects)**

![Image not Available](/assets/Fig93.png)

## Delete topic ##

You can delete existing topic in two ways:

**Step 1:** Navigate to **Browse topics**.

**Step 2:** Select a topic that you want to delete and the **Topic details** page displayed.

**Step 3:** Click ![Image not Available](/assets/icon9.png) icon and select **Delete**. A confirmation window appears to confirm, if you are sure to delete the topic and all it's subtopics under this topic will be deleted. **Subscriptions** from this topic will also be deleted. 

**Step 4:** Tick ![Image not Available](/assets/icon10.png) icon and click **Delete**. 

Once the topic is deleted, it will not appear in the **Browse topics** page.

- Alternatively you can do the following:

**Step 1:** Navigate to **Projects** page, select a project name.

**Step 2:** Click **My topics** tab.

**Step 3:** Select a topic that you want delete. 

**Step 4:** Click ![Image not Available](/assets/icon9.png) icon and select **Delete**. A confirmation window appears to confirm if you are sure that you want to delete the topic and all its subtopics under this topic will be deleted. 

**Step 5:** Tick ![Image not Available](/assets/icon10.png) icon and click **Delete**. 

When topic is deleted, it's subtopics are also deleted, Subscriptions to this topic and its subtopics will also be deleted. 

![Image not Available](/assets/Fig54a.png)

You can also delete topic that are pending or suspended.

**Subscribers**

In this tab you can view the topic subscribed details: 

- Date - the date of the project subscribed
- Project name - the project used for subscribe to the topic
- Agency - the name of the agency subscribed
- Project description - the description of the susbcribed project 
- Status

![Image not Available](/assets/Fig79.png)

**Adaptor**

- Adaptor detail
- +Create new adaptor

![Image not Available](/assets/Fig80.png)

**Create new adaptor**

- How to **Create new adaptor**

![Image is not available](/assets/vid2howtocreatenewadaptor.gif)

- To **create new adaptor** you can do the following:

**Step 1:** In Adaptor tab, Click **+Create new adaptor**.

**Step 2:** In **Create adaptor** form , enter **Name**.

**Step 3:** Enter description in **Description** field.

**Step 4:** For **Request** Method **GET**, Enter the **Endpoint** URL.

**Step 5:** Select **Body type** as none.

**Step 6:** Select **Active adaptor** toggle.

**Step 7:** Click **Create**.

**Note:** Custom corn experssion should not be less than 5 minutes.

After you have created adaptor you could see the following in **Adaptor** tab

- Adaptor details
- Adaptor logs

Under **Adaptor details**, you can see the following:

- Edit button - to update Adaptor details
- Name
- Description
- Status - Pending, Active, Blocked, Suspended
- Created date
- Updated date

Information about the Status of **Adaptor**

- Adaptor **Pending** - status, if any one of **Edit adaptor** form input fields need to be updated from UI, then the status of the adaptor will be pending.

![Image not Available](/assets/Fig105_32.png)

![Image not Available](/assets/Fig105_31.png)

- Adaptor **Active** - status where the adaptor is Active.

![Image not Available](/assets/Fig81.png)

- Adaptor **Blocked** - HTTP adaptor might be blocked when source is down for long period. But it will be auto re-activated periodically.

![Image not Available](/assets/Fig105_30.png)

- Adaptor **Suspended** - status when the source will be turn down manually for some period of time.

![Image not Available](/assets/Fig105_33.png)

Under **Activity log**, you can see the following:

- Timestamp
- Status - Success, Triggered, Failed and Blocked
- Reason
- Search activities
- Filter by **Date range** and Adaptor **Status**

![Image not Available](/assets/Fig82.png)

**Note:**

- Once the adaptor **status=Failed** you can see **status=Blocked**.
- You as a publisher, you will be notified by email for adaptor **status=Blocked**.

![Image not Available](/assets/Fig84.png)

You can do Filter by **Date range** and Adaptor **Status**
![Image not Available](/assets/Fig85.png)

As a **Subscriber** you can see the following:

- See the topic overview
- See folders and its subfolders within the topic
- Subscribe to the topic
- See the status of the topic
- View payload
- Payload last seen time
- Copy large payload to clipboard

**Topic details** page

![Image not Available](/assets/Fig78.png)

After you have **subscribed** to the topic, you can preview the content by clicking **View payload**, can seePayload last seen time**, subscriber can see **Payload last seen time**.

![Image not Available](/assets/Fig83.png)

Subscriber can **Copy large payload to clipboard**

![Image not Available](/assets/Fig105_16.png)
