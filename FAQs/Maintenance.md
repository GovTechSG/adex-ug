# FAQ about maintenance
FAQs for account includes questions about maintenance.

## What is a maintenance window?

A maintenance window is a scheduled period of time during which a system or service may be temporarily unavailable or disrupted due to maintenance activities.

## Why is a maintenance window necessary?

Maintenance activities are necessary to ensure that systems and services are running smoothly and securely. Regular maintenance helps to prevent unexpected downtime and ensures that systems are up-to-date with the latest security patches and updates.

## When is the scheduled maintenance window for ADEX?

The scheduled maintenance window for ADEX is every Wednesday evening from 6PM to 12AM Thursday morning (SGT). However, please note that we may not have a maintenance window every week. If we do schedule a maintenance window, we will use the specified window and inform users via email at least 3 working days in advance. 

## How can I subscribe to or unsubscribe from ADEX email notifications?

To submit your request, please submit your request via this link https://go.gov.sg/adexsupport. Our team will review your request and respond to you as soon as possible. 

## Will the whole ADEX System be down during a maintenance window?

During a maintenance window, either or both services (Portal and Broker Service) of the ADEX System may be affected. While it is rare for the broker service to be down, it is still possible and users should look out for maintenance window notifications to determine which service(s) will be unavailable. It is the responsibility of users to plan their activities accordingly and complete any necessary tasks before the maintenance window begins. We recommend that users regularly check for maintenance window notifications and stay informed about any potential service disruptions. 

## What does it mean for the Portal service to be down during a maintenance window?

If the Portal service is down during a maintenance window, it means that users will not be able to access the user-facing component of the ADEX System. This may include features such as logging in, creating projects, browsing topics, and managing user accounts. During this time, users may experience intermittent errors or be unable to access the Portal service at all. 

If **only** the Portal service is down for maintenance, please note that only the Portal service may have service interruption. The message transmission and queue will be unaffected, and users will still be able to exchange data through the Broker service.

## What does it mean for the Broker service to be down during a maintenance window?

If the Broker service is down during a maintenance window, it means that the backend component of the ADEX System that facilitates the exchange of data between different systems will be unavailable. This may affect the ability of users to send or receive data through the system. During this time, users may experience errors or be unable to exchange data through the Broker service at all. 

## What happens if the Broker service is down during a maintenance window for ADEX?

If the Broker service is down during a maintenance window for ADEX, please note the following:

a) Your MQTT Client may experience intermittent connection to the ADEX's Broker service.

b) Your MQTT Client will queue the Payload/Message(s) at the client's side.

c) Upon the next successful connection, your MQTT Client will resume data transmission to the ADEX's Broker service.

Once the maintenance activities are complete, the Broker service will be restored and users will be able to exchange data through it again. 

## Are there any particular settings that need to be enabled on the MQTT Client to enable message queuing at the client's side when the Broker Service is down?

No, there are no particular settings that need to be enabled on the MQTT Client. The MQTT library takes care of message queuing at the client's side automatically when the Broker Service is down. This means that the Payload/Message(s) will be queued at the client's side and transmitted to the Broker service upon the next successful connection.

## Will there be enough space to hold my queue while the ADEX system is undergoing maintenance activities?

Yes, there should be enough space to hold your queue while the ADEX system is undergoing maintenance activities. The amount of space required to hold the queue will depend on the size and frequency of the Payload/Message(s) being transmitted. However, the MQTT library is designed to handle large volumes of data and should be able to handle most use cases. 

## What should I do after the maintenance window to ensure that my data transmission has been resumed normally, and is there an auto-reconnect feature available for the MQTT client?

After the maintenance window, you should reconnect your MQTT client to the ADEX's Broker service to ensure that your data transmission has been resumed normally. To verify that your data transmission has been resumed normally, you will need to check that your MQTT client is connected successfully and that any queued Payload/Message(s) have been transmitted successfully.

To make this process easier, we recommend that you enable the auto-reconnect feature on your MQTT client. This will allow your client to automatically reconnect to the ADEX's Broker service if the connection is lost for any reason. 


