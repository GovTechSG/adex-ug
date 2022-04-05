
### Generate Cert ###

After creating a new project, go to **Connections** tab. This tab shows the **connection strings** and **SSL certificates** to setup MQTT connection. 

- Cert status - Active, Expired
- Unique MQTT URL
- Unique MQTT Client ID
- Client key
- Client secret
- SSL Certificate chain
- SSL Client certificate
- SSL Private key - this box will be shown once 
- Private key password - you will receive this in your email.

![Image not Available](/assets/Fig36.png)

**Note**: User need to copy and save all the 3 SSL certs as .pem file using a text editor.

If user didn't save the certs file for the first time, user can regenerate the certs by clicking **Generate new certificate** button.

![Image not Available](/assets/Fig99f.png)

User will receive a **Private key password** through email and use that password in the **Client key passphrase** for your MQTT client set up.

![Image not Available](/assets/Fig38.png)

 User will receive the email for **project cert expires soon**!

 User will receive the **Project cert expires soon!** email, 30 days before the 3 certs expires!
 
![Image not Available](/assets/Fig99k.png)
 
 - After the certs have expired, user will still receive the **project expired!** email for the next 7 days.
 
![Image not Available](/assets/Fig99e.png)

From the portal, user can see the certs **status=Expired**, user can click the **Generate new certificate** button to start using the MQTT client again.

![Image not Available](/assets/Fig99m.png)


 To set up **MQTT Client connection**:
 
 How to **set up MQTT connection**:
 
 ![Image not Available](/assets/vidsetupmqttcon.gif)

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

 **Note**: *Topic path should be copied from topic details page.*
 
 ![Image not Available](/assets/Fig69.png)

**Important**: A **Subscriber** must subscribe to the topic from the portal first.

**Step 5:** Enter the topic path and fill into the **Topic to subscribe** field. Click the **Subscribe** button to receive data for this topic.

![Image not Available](/assets/Fig42.png)

**Recommended MQTT topic path pattern hierarchy**

It is best to have a consistent approach in naming the topics for ease of integration to 3rd party application.

The proposed approach is to construct the topic name based on the following information:

{agency}-{client_id}/{message type}/{reading type}/{deviceId}

{agency}-{client_id}/{category}/{sub-category}/{deviceId}

**Here is a list of examples:**

nea-ab1c23/environment/psi/device001

nea-ab1c23/environment/temperature/device001

#### Payload format ####

 - Maximum payload size is 1MB.
 - The payload content should be as minimal as possible and can be grouped together when they make sense. 
 - This is to ensure that clients do not incur data charges when not needed.

**Example payload format**

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





