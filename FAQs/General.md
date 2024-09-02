# FAQs about General

This includes general questions about ADEX, publish-subscribe-based messaging protocol or MQTT, and difference of ADEX to APEX. 

## What is ADEX? 

**ADEX** stands for **Asynchronous Data Exchange**, a centralised data exchange platform for the Whole-of-Government (WOG). It is part of the Strategic National Project under Smart Nation Sensor Platform (SNSP).

**ADEX** enables government agencies to publish and subscribe to real-time data using a self-service portal that will run in Government Commercial Cloud (GCC) both in the internet and intranet.

## What is MQTT?

Message Queue Telemetry Transport (MQTT), is a publish-subscribe-based messaging protocol based on ISO standard ISO/IEC PRF 20922. It works over TCP/IP. It is designed to be lightweight for small, low power, and low bandwidth device communication. MQTT is the most common protocol used in Internet Of Things (IOT).

## What is the difference between ADEX and APEX?

Both **ADEX** and **APEX** are self-service data sharing platform for the Whole-of-Government.

**APEX** enables users to directly communicate in terms of requesting and granting access to APIs. It acts as a centralized and secure API gateway.

It uses request-response architecture, each client opens a direct connection to each server, because the client request data directly from the server. A one-to-one distribution process.

The equivalent is like SMS used for sending message to a recipient. Another example, is newspapers where you go to a store to buy or get it delivered to your house.

For more information about **APEX**, refer to this [link](https://www.developer.gov.sg/technologies/data-and-apis/apex). 

**ADEX** is a platform for real-time, asynchronous fire-and-forget data transfer.

It uses pub-sub transport messaging protocol (MQTT), which allows clients to publish and subscribe to a channel and receives messages as they become available. A one-to-many distribution process.

The equivalent is like WhatsApp mobile app where you can group chats. Another example is radio news where you tune in to a channel.

One advantage of ADEX, it is good for frequent traffic and lightweight networks. It reduces network load and clients are pushed the latest data. ADEX will work not only with sensor, but also with non-sensor and streaming data.

You can check relevant information about request-response versus publish-subscribe [here](https://blog.opto22.com/optoblog/request-response-vs-pub-sub-part-1) and which one to use [here](https://blog.opto22.com/optoblog/request-response-vs-pub-sub-part-2).

## Does ADEX encrypt or decrypt my data/payload?

ADEX uses the Transport Layer Security (TLS) to encrypt data in transit. There is no encryption and decryption of data facilitated by ADEX. Data providers and data consumers are recommended to enforce encryption, e.g., JSON Web Encryption (JWE), to protect sensitive data at rest and in transit.

## As a government agency user or business user of ADEX, we need to develop our own MQTT client to connect to ADEX Broker, but we’re not familiar with MQTT. Is there any resource available?

ADEX User Guide has demo MQTT sample codes for reference at this [link](https://docs.developer.tech.gov.sg/docs/adex-user-guide/User%20Guide/Projects?id=mqtt-client-sample-code).

## The SSL certs that are generated from the ADEX Portal has a validity of 2 years. How do we generate new certs to replace the expiring one?

Refer to this URL [link](https://docs.developer.tech.gov.sg/docs/adex-user-guide/User%20Guide/Projects?id=generate-cert).

## I'm not sure if my SSL certs are still valid. How do I check?

Log in to ADEX Portal > Select the project you want to check for the cert's validity > Click on "Connection" > Mouse over "Cert status" to see the popup message.

## Where can I find information about the maintenance window?

Refer to this URL [link](https://docs.developer.tech.gov.sg/docs/adex-user-guide/FAQs/Maintenance).

## I need to whitelist new IP address. How do I proceed with my request?

Fill in this request form and submit at [ADEX Support](https://go.gov.sg/adexsupport).

## How to Ensure You Have Downloaded All Necessary Information for Certificate Generation

To verify that all connection credentials are correctly set up for your Publish and Subscribe project, refer to the image files below:

![Image not Available](/assets/Fig106_2.png)

![Image not Available](/assets/Fig106_1.png)

## Required MQTT Connection Credentials

The following credentials are essential for establishing an MQTT connection and can be generated from the ADEX Portal:

1. **MQTT URL:** 
2. **MQTT Client ID:** 
3. **Client Key** (optional): 
4. **Client Secret** (optional): 

### Certificates and Keys

- **Certificate Chain (ca.pem):** Downloaded as a `.PEM` file.
- **Client Certificate (client.pem):** Downloaded as a `.PEM` file.
- **Private Key (private.pem):** Downloaded as a `.PEM` file.
- **Private Key Password:** ADEX will send this via email.

### Topic Path

- **Topic Path:** The topic to be published/subscribed from ADEX.
