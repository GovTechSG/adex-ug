# FAQs about Messaging

FAQs for messaging includes questions about inputs required to connect to ADEX broker and disconnection to MQTT. 

## Why is my MQTT connection disconnecting? 

You are using a duplicate MQTT Client ID across your different MQTT connections. MQTT Client ID should be unique in the exchange. You can generate one using a UUID.

## What are the inputs required to connect to ADEX broker?

Inputs required to connect to ADEX broker:

- Unique MQTT Client ID
- Client key
- Client secret
- SSL CA file
- SSL Client cert
- SSL private key
- Private key password

All required and obtainable from the ADEX Portal.

## Why is my MQTT client not able to connect to ADEX?

Make sure you have provided your IP address for the support team to open the firewall.

Check the connection settings on your client and ensure that the passwords are entered correctly.

Check your SSL certificates are in valid format. Refer to [this page](https://www.ssl247.com/kb/ssl-certificates/troubleshooting/certificate-matches-private-key) on how to check.

For example, check the private key file is ok using this command:

openssl rsa –noout –modulus –in <file>.key | openssl md5

## Any authentication needed for MQTT connection?
  
Valid SSL certs generated from ADEX portal is required to connect.
  
  
  
 
