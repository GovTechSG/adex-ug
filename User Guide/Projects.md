
# Projects

A project is a collection of topics, **project type** could be a published or subscribed.

It contains **Connection** strings and **SSL certificates** to set up an MQTT (Message Queuing Telemetry Transport) connection. MQTT is a messaging protocol to connect to the broker. In MQTT, a publisher publishes messages on a topic and a subscriber subscribes to that topic to view the message. 

MQTT connection is recommended to **Publish** and **Subscribe** topics on ADEX. **AMQP** is also supported.

To **Publish** the information, you must first create your own project to **Create topic**. A topic cannot be duplicated and cannot published and subscribed by the same project.

**Subscriber** roles can only create **Subscribe type** project. 
**Publisher** roles can create both project types.

In **Projects** page, you can see list of all **Publish** and **Subscribe** projects containing number of topics being grouped together. Select a project to see **project details**, **connection status**, **published** or **subscribed topics**, and it's **activity** log.

![Image not Available](/assets/Fig32b.png)

You can **create new project** by clicking **Create** button on the top right of the **Browse topics** page and select **New project**.

![Image not Available](/assets/Fig31.png)

Or, click **Projects** from the left side navigation bar.

![Image not Available](/assets/Fig32.png)

### Create new project ###

To **Create project**:

**Step 1:**	Click **Create project**. The projects page is displayed. 

**Note:** *For your first project, you will see this page as shown below.*

![Image not Available](/assets/Fig33.png)

**Step 2:**	Enter the following information:

  - Project name
  - Team - Once you select a team, you can choose the type of project
  - Project type - Publish, Subscribe
  - Project duration
  - Description

![Image not Available](/assets/Fig34.png)

Click **Create**. The newly created project appears in the list of project in the Project page.

![Image not Available](/assets/Fig51a.png)

**Note** 

- You can **update** the project by clicking **Save**, after you have updated the project, you will receive an **email notification**.

![Image not Available](/assets/Fig99g.png)

- You can **delete** the project by clicking **Delete**, after you have deleted the project, the topics attached to the project will be deleted and you will receive **email notification**.

![Image not Available](/assets/Fig99h.png)

- You can **Search projects**

![Image not Available](/assets/Fig99i.png)

- You can use **Filters** to filters projects by:

    - Project type - Publish, Subscribe
    - Date created
    - Organisation
    - Sort by - A-Z, Z-A
    - Team
    - Clear all filters

![Image not Available](/assets/Fig99j.png)

**Note** *You can use **Clear all filters** to reset the filters.*

You will receive a notification email when your **project expired**, You may extend the project period before it get suspended.

![Image not Available](/assets/Fig99d.png)

To extend the **Project duration**:

**Step 1:** Go to **Project** and search for project to update the project duration. 

**Step 2:** Select project to view the project details.

**Step 3:** Under **Project duration**, change the project dates.

![Image not Available](/assets/Fig36d.png)

**Step 4:** Click **Save** to save the project details successfully. 

In the Projects page, displays the **Project name**, **Organisation**, **Created by**, **Created date**, It also includes the following tabs:

![Image not Available](/assets/Fig35.png)

- **Overview** – Displays the details of the project.
- **Connections** – Displays the details to set up and connect to MQTT Client.
- **My topics** – Shows the published topics under the project and the total count.
  **Note:** *This tab is only available for a Publisher only.*

- **Subscribed topics** – Shows the subscribed topics by the project and the total count.
  **Note:** *This tab is available for Publisher and Subscriber.*

![Image not Available](/assets/Fig59.png) 

- **Activities** - Displays the audit trail of the project.


### Set up MQTT connections ###

After creating a new project, go to **Connections** tab. This tab shows the **connection strings** and **SSL certificates** to setup MQTT connection. 

- Cert status - Active, Expired
- Unique MQTT URL
- Unique MQTT Client ID
- Client key
- Client secret
- SSL Certificate chain
- SSL Client certificate
- SSL Private key 
- Private key password - you will receive this in your email.

![Image not Available](/assets/Fig36.png)

 **Note:** *The **Private key password** for the projects, you will receive in your email. You must copy and save the certificates in a .PEM text editor file.*
 
 ![Image not Available](/assets/Fig99f.png)

 - Alternatively, click **Generate certificate** button to generate new certificate if your **project certificate is expired!**

 ![Image not Available](/assets/Fig99e.png)
  
 You will receive a **Private key password** through email and use that password in the **Client key passphrase** for your MQTT client set up.

![Image not Available](/assets/Fig38.png)


To set up **MQTT Client connection**:

**Step 1:**	Copy the certificates in a text Editor and save each as .PEM file separately.

**Step 2:**	Now, open MQTT Client.

![Image not Available](/assets/Fig39.png)

**Step 3:** Click **Create MQTT Client**.

**Step 4:** Set up MQTT connections with the following:

- **MQTT Client Name** – Name is not specific and can give random name
- **Protocol** - Select protocol. For example, *mqtt/tls*
- **Host** - Enter **Unique MQTT URL** 

- Upload each file you copied in a text editor in the following fields: 

  - CA file
  - Client certificate file
  - Private key file

- Enter the password received from the email inbox in the **Client key passphrase** field

![Image not Available](/assets/Fig40.png)

- Click **Save** and connected successfully.

As a **Publisher** you are now ready to publish a topic.

![Image not Available](/assets/Fig41.png)

 **Note** *Topic path should be copied from topic details page.*

A **Subscriber** needs to subscribe to this topic from the portal.

**Step 5:** Enter the topic path and fill into the **Topic to subscribe** field. Click the **Subscribe** button to receive data for this topic.

![Image not Available](/assets/Fig42.png)

Here is an example of MQTT code samples. Download the files and use for reference.

- <a href="/assets/java.zip" download>Click to download</a> java.zip.

- <a href="/assets/node.zip" download>Click to download</a> node.zip.

- <a href="/assets/python.zip" download>Click to download</a> python.zip.

- <a href="/assets/golang.zip" download>Click to download</a> golang.zip.

For more related information about MQTT, refer to this [link](https://www.hivemq.com/blog/mqtt-essentials-part-3-client-broker-connection-establishment/).


### Set up MQTT topic name and payload format ###

Ideally, it is important to design a topic naming and structure within the payload. 

In this section, provides a guideline on how to construct the topic name and payload content for MQTT networks. 


#### Topic format ####

It is best to have a consistent approach in naming the topics for ease of integration to 3rd party application. 

The proposed approach is to construct the topic name based on the following information:

```
{agency}-{client_id}/{message type}/{reading type}/{deviceId}
{agency}-{client_id}/{category}/{sub-category}/{deviceId}
```

Here is a list of examples:

```
nea-ab1c23/environment/psi/device001
nea-ab1c23/environment/temperature/device001
nea-ab1c23/environment/humidity/device001
nea-ab1c23/env/device001
```

#### Payload format ####

The payload content should be as minimal as possible and can be grouped together when they make sense. 

This is to ensure that clients do not incur data charges when not needed.

***SensorML Format***

```javascript
[
    {"n":"urn:dev:ow:10e2073a01080063", "v":23.1}
]
```

```javascript
[
    {"bn":"gateway", "n":"temp", "u":"Cel", "v":23.1},
    {"bn":"dev1", "bv":200, "n":"distance", "u":"m", "v":1}
]
```

For more related information about SensorML format, refer to the following link:
- [IETF RFC-8428](https://tools.ietf.org/html/rfc8428)
- [SenML Dictionary](https://www.iana.org/assignments/senml/senml.xhtml)
- [Examples](https://www.elastetic.com/wp/2018/05/20/senml-messages/) 


***Alternatively:***

**nea-ab1c23/environment/humidity/device001**

```javascript
{
    "id": "device001",
    "loc": {
        "lat": 13.361389,
        "lon": 38.115556
    },
    "humidity": {
        "v": 67.00,
        "uom": "%"
    }
}
```

**nea-ab1c23/environment/psi/device001**

```javascript
{
    "id": "device001",
    "loc": {
        "lat": 13.361389,
        "lon": 38.115556
    },
    "psi": {
        "v": 24
    }
}
```

**nea-ab1c23/traffic/radar/device001**

```javascript
{
    "id": "device001",
    "loc": {
        "lat": 13.361389,
        "lon": 38.115556
    },
    "radar": {
        "angle": {
            "v": 22,
            "uom": "degree"
        },
        "speed": {
            "v": 32.6,
            "uom": "m/s"
        },
        "direction": "into compound"
    }
}
```

**nea-ab1c23/environment/rain/device001**

```javascript
{
    "id": "device001",
    "loc": {
        "lat": 13.361389,
        "lon": 38.115556
    },
    "rain": {
        "s": "off"
    }
}
```

**nea-ab1c23/environment/temperature/device001**

```javascript
{
    "id": "device001",
    "loc": {
        "lat": 13.361389,
        "lon": 38.115556
    },
    "temperature": {
        "v": 24.0,
        "uom": "C"
    }
}
```

For the **environment** topic, it can contain multiple measurements like **humidity**, **psi**, **rain**, and **temperature** grouped together.

**nea-ab1c23/environment/sensors/device001**

```javascript
{
    "id": "device001",
    "loc": {
        "lat": 13.361389,
        "lon": 38.115556
    },
    "humidity": {
        "v": 67.00,
        "uom": "%"
    },
    "psi": {
        "v": 24
    },
    "rain": {
        "s": "off"
    },
    "temperature": {
        "v": 24.0,
        "uom": "C"
    }
}
```

***Common Payload Snippets***

**Time**                                                                                                                       

Time is denoted by the Unix epoch timestamp in seconds. Use milliseconds if readings are expected to be very frequent.

> **SenML**                                                                             

```javascript
{
  "t":1.577836800e+09
}
```

t: timestamp - double (seconds)                                                       


> **Traditional**

```javascript
{
    "ts": 1577836800000
}
```

ts: timestamp - double (milliseconds)

Alternative:
"timestamp": 1577836800 (seconds)


**Status/State**                                                                                                                

> **SenML**                                                                             

```javascript
{
    "u":"/", "v":1
}
```

u: unit - string
v: value - double                                                      


> **Traditional**

```javascript
{
    "s": "on"
}
```

s: state - string

Alternative:
"v": 1
"state": "on"
  
  
**Measurement**                                                                                                                 


> **SenML**                                                                             

```javascript
{
    "u":"m", "v":80
}
```

u: unit - string

v: value - double
- v: numeric values
- vb: boolean values
- vd: binary data
- vs: strings

> **Traditional**

```javascript
{
    "measure": {
        "v": 80.0,
        "uom": "%"
    }
}
```

```javascript
{
    "measure": 80.0
}
```

measure: measure name - block
v: value - double
uom: unit of measure - string

  
**Location**                                                                                                                    

GPS location includes lat, lon, alt, and a timestamp for a moving sensor. Ground sensors may not have altitude reading. Location for immobile sensor helps to enable visualisation on a map. Timestamp is Epoch time in milliseconds.

> **SenML**                                                                             

```javascript
{"u":"lat","v":13.361389,"t":1.577836800e+09},
{"u":"lon","v":38.115556,"t":1.577836800e+09},
{"u":"alt","v":20.112233,"t":1.577836800e+09}
```
```javascript
[
    {"bn":"urn:dev:ow:10e2073a01080063","bt":1.577836800e+09},
    {"u":"lat","v":13.361389},
    {"u":"lon","v":38.115556},
    {"u":"alt","v":20.112233}
]
```

- lat: latitude - float
- lon: longitude - float
- alt: altitude - float
- t: timestamp - double (milliseconds)
- bt: base timestamp - double (milliseconds)
- bn: base name (base name of the device)                                                   


> **Traditional**

```javascript
{
    "loc": {
        "lat": 13.361389,
        "lon": 38.115556,
        "alt": 38.115556,
        "ts": 1577836800000
    }
}
```

- loc: location - block
- lat: latitude - float
- lon: longitude - float
- alt: altitude - float
- ts: timestamp - double (milliseconds)
  
#### Recommended MQTT topic path pattern hierarchy #### 
  
Here is a recommended MQTT topic path pattern hierarchy for easy categorisation and browsing. 

MQTT topic path pattern should follow a recommended hierarchy. This is recommended but not enforced. Using a hierarchy, allows easier subscribing of all children topics under a category.  

```
Topic Path: {agency}-{client_id}/{category}/{sub-category}/{deviceId}

Example: nea-ab1c23/environment/temperature/device001
```

Categorising MQTT topics for browsing (with synonyms):


| Topic                          | Synonyms    |
|:-------------------------------|:------------|
| environment (climate, weather) | forecast    |
|                                | humidity    |
|                                | noise       |
|                                | rainfall    |
|                                | temperature |
|                                | wind        |
|                                | tide        |
| emergency                      | alerts      |
|                                | cardiac     |
|                                | drowning    |
|                                | accidents   |
|                                | pullcords   |
|                                | fires       |
| security                       | cctv        |
|                                | cameras     |
|                                | incidents   |
| community                      | alerts      |
|                                | events      |
| utility                        | electricity |
|                                | water       |
| traffic                        | cameras     |
|                                | incidents   |
|                                | roadworks   |
|                                | roadblocks  |
| devices                        | status      |
| analytics                      | reports     |
| system                         | metrics     |




### Set up AMQP connection ###

For 2-way SSL connection, use the same PEM files as MQTTS: ca.pem, client.pem, private.key, clientid and clientkey are required.


**Exchange:** amq.topic

**Routing key for publish:** Full topic pattern with dot (. ) instead of slash (/ )
 
> **Publish:**

```javascript

channel.Publish(
            "amq.topic",        // exchange
            $topic,             // routing key
            false,              // mandatory
            false,              // immediate
            amqp.Publishing{
                DeliveryMode: amqp.Transient,
                ContentType:  "application/json",
                Body:         $payload,
                Timestamp:    time.Now(),
            })

```

**Binding key for subscribe:** Full topic pattern with dot (. ) instead of slash (/ )

> **Subscribe:**

```javascript

q, err := channel.QueueDeclare(
        "",    // name, leave empty to generate a unique name
        false, // durable
        true,  // delete when unused
        false, // exclusive
        false, // noWait
        nil,   // arguments
    )
 
err := channel.QueueBind(
        q.Name,         // name of the queue (generated from above step)
        $topic,         // bindingKey, topic pattern with . seperator
        "amq.topic",    // sourceExchange, must use "amq.topic" for MQTT topics
        false,          // noWait
        nil,            // arguments
    )
 
replies <-chan amqp.Delivery
replies, err := channel.Consume(
        q.Name,         // name of the queue (generated from above step)
        $consumerTag,   // consumer tag (consumer "id", eg. mqtt_clientid)
        true,           // auto-ack
        false,          // exclusive
        false,          // no-local
        false,          // no-wait
        nil,            // args
    )

```

For more related information about AMQP, refer to this [link](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-amqp-protocol-guide).

## My topics ##

After creating a project, create your first topic. The **My topics** tab is only available for **Publisher**. This tab shows the topic that you have published for this project.


To **Create topic**:

**Step 1:** Navigate to **Projects** page > **My topics** tab. Click **Create topic**.

![Image not Available](/assets/Fig43.png)

**Step 2:** Select a type of topic if you want to create a new one or add as a sub-topic. Click **Next**.

![Image not Available](/assets/Fig43e.png)

**Step 3:** Select from the option who can see the topic. Click **Next**.

- Public
- All government agencies
- Only my agency
- Only to my team
- Only me

![Image not Available](/assets/Fig44.png)

**Step 4:**	Select data classification. Click **Next**.

![Image not Available](/assets/Fig45.png)

**Step 5:**	Select the project and enter topic name. Click **Next**.

![Image not Available](/assets/Fig46.png)

**Step 6:**	Fill in the following details of the topic.

- **Topic description** – Enter description to the topic
- **Tags** – Add tags to the topic maximum of 5 tags
- **Is approval needed for subscription requests?**
  - **Yes** – Approval is needed from publisher before you subscribe 
  - **No** – Allows free access to the topic and no approval needed from the publisher
- **Also publish on ADEX On-prem**
  - **Yes** - you can select the on-prem projects
  - **No** - no On-prem projects for this topic

![Image not Available](/assets/Fig47.png)

**Step 7:** Click **Create**. The new topic is created successfully.

![Image not Available](/assets/Fig69.png)

You can see the newly created topic being added in **Projects** page > **My topics** tab.

![Image not Available](/assets/Fig49.png)

You can add more topics within the topic on your own project by selecting from topic folders and clicking the ![Image not Available](/assets/icon9.png) icon.

### Add topic within a topic ###

To add **New topic** as sub-topic:

**Step 1:**	Navigate to **Projects** page > **My topics** tab. 

**Step 2:**	Select a topic and click ![Image not Available](/assets/icon9.png) icon.

**Step 3:** Click **New topic**. A new window appears to create new topic.

![Image not Available](/assets/Fig48.png)

**Step 3:**	Enter topic name and click **Create**.

![Image not Available](/assets/Fig52.png)

The newly created topic is added successfully in the Topic Details page.


### Edit topic ###

To edit topic:

**Step 1:**	Navigate **Projects** page, select your project. 

**Step 2:** Click **My topics** tab.

**Step 3:**	Select a topic to edit and the **Topic details** page displayed. 

**Step 4:**	Click **Edit**. A new window appears to edit the details of the topic.

![Image not Available](/assets/Fig54.png)

**Step 4:** Click **Update**.

### Suspend Topic ###

Suspend the topic allows to disconnect the topic so you will not receive any payload for this topic.

When a topic has been **Suspended**, you can still edit and Subscribers can still subscribe to this topic.

To **Suspend** a topic:

**Step 1:**	Navigate **Projects** page, select your project. 

**Step 2:** Click **My topics** tab.

**Step 3:** Select a topic and click ![Image not Available](/assets/icon9.png) icon.

![Image not Available](/assets/Fig55b.png)

**Step 4:** Click **Suspend** and the status becomes **Suspended**.

![Image not Available](/assets/Fig99a.png)

 **Note:** *Data for **Suspended** topic cannot be published in MQTT client.*

You can **Unsuspend** the topic by clicking **Unsuspend** and the status of the topic is **Active**.

![Image not Available](/assets/Fig99b.png)


In the **Browse Topic** page, you can see the topic has been **Suspended** by the greyed out font and icon.

![Image not Available](/assets/Fig99c.png)

**Note** *To subscribe the topic, you need publisher approval.*

### Pending topic ###

Pending topic, is when the **Publisher** published the topic through MQTT without being first created from the portal.

The **Publisher** allows to verify if the topic is a valid topic.

To view **Pending** topic:

**Step 1:** Navigate to **Projects** page and select a project.

**Step 2:** Click **My topics** tab, a topic with status **Pending** is displayed.

![Image not Available](/assets/Fig56b.png)

You can **Edit the details** of this topic and update. Also, it allows you to **Publish** the topic and the status changed to **Active**.

![Image is not available](/assets/vidhowtoeditandpublishpendingtopic.gif)

### Unposted topic ###

Unposted topic is detected by the system. It should be initialised by the **Publisher** to publish in portal.

**Step 1:** Navigate to **Projects** page and select a project.

**Step 2:** Click **My topics** tab, select a topic.

**Step 3:** Click an unposted topic and click ![Image not Available](/assets/icon9.png) icon.

**Step 3:** Click **Initialise topic**.

**Step 4:** Click **Edit the details** before initialising, alternatively click **Create**. A new pop-up window appears to update the topic details.

**Step 5:** Click **Create topic**. Topic status becomes **Active**.

![Image is not available](/assets/vidintialiseunpostedtopic.gif)

## Subscribed topics ##

Both **Publisher** and **Subscriber** can subscribe to a topic. Both publisher and subscriber can view the **Subscribed topics** tab.

To **Subscribe** to a topic:

**Step 1:**	Navigate to **Projects** page > Click any **Subcribe** project > Click **Subscribed topics** tab. Click **Browse topics**.

![Image not Available](/assets/Fig55a.png)

**Step 2:**	Select the topic card that you want to subscribe.

![Image not Available](/assets/Fig56.png)

**Step 3:**	Once the topic card is selected, the **Topic details** page is displayed. Click **Subscribe**.

![Image not Available](/assets/Fig57a.png)

**Step 4:**	Select a project to subscribe to the topic. Click **Subscribe**.

![Image not Available](/assets/Fig58.png)

**Step 5:**	Go back to **Projects** and click **Subscribed topics** tab. The new subscription is added to the subscribed topics.

![Image not Available](/assets/Fig59.png)

## Activities ##

**Step 1:** Navigate to **Projects** page. Click a project name. 

**Step 2:** Click **Activities** tab.

**Step 3:** You can see the following:

- UUID
- Date
- Service 
- Action - Create and Update
- Action description
- Payload

![Image not Available](/assets/Fig94.png)

**Step 3:** You can **Search activities**. 

![Image not Available](/assets/Fig96.png)

**Step 3:** You can do **Filters** by the following:

- Type of action - Create, Update, Delete and All

![Image not Available](/assets/Fig98.png)

- Date created
- Service - Topic, User, Project, Subscription, Adaptor, Message and All

![Image not Available](/assets/Fig99.png)

- User UUID
- Clear all filters 

![Image not Available](/assets/Fig97.png)

**Step 4** You can click **Clear all filters** to reset the filters.



