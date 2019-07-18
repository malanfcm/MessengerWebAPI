# MessengerWebAPI
###### All of the below is tentative and may change at any point in time. This document will be updated accordingly.

## Authentication
Postman Collection
[Use Case 7](/RXMessengerAPI.docx)
________________________________________________

To use any of the functionality in the MessengerWebAPI you will need to Authenticate yourself with your APIKey. Once authenticated you will receive back a JWT which is required as a header for all subsequent API Requests.

API Keys will be generated at a later stage and Distributed accordingly

- Method: POST
- URL: https://localhost:5001/api/auth/authenticate
- Content-Type: application/json
- Headers: none
- Body:
  - {
  
      "apiKey": "",
      
      "token": null
      
    }

________________________________________________

## Messenger Web API
Postman Collection
[Use Case 6 ](/RXMessengerAPI.docx)
________________________________________________

###### Test API Request:

- Method: GET
- URL: https://localhost:5001/api/messaging/Test
- Content-Type: application/json
- Headers: 
  - Key: Authorization
  - Value: Bearer (FOLLOWED BY JWT TOKEN WITHOUT BRACKETS)
- Body: none

________________________________________________

###### GetBatch API Request:

- Method: POST
- URL: https://localhost:5001/api/messaging/AckBatch
- Content-Type: application/json
- Headers: 
  - 1
    - Key: Authorization
    - Value: Bearer (JWT TOKEN)
- Body: none

________________________________________________

###### AckBatch API Request:

- Method: POST
- URL: https://localhost:5001/api/messaging/GetBatch
- Content-Type: application/json
- Headers: 
  - 1
    - Key: Authorization
    - Value: Bearer (JWT TOKEN)
  - 2
    - Key: Content-Type
    - Value: application/json
- Body: 
  - {
  
      "batchId": (BATCH ID RETURNED FROM GetBatch),
      
      "batchMessageCount": (BATCH MESSAGE COUNT RETURNED FROM GetBatch),
      
      "batchNote": ("BATCH NOTE IF ANY")
      
    }

________________________________________________

Postman Collection
[Use Case 8 ](/RXMessengerAPI.docx)
________________________________________________

###### EditMsgStatus API Request:

- Method: POST
- URL: https://localhost:5001/api/messaging/EditMsgStatus
- Content-Type: application/json
- Headers: 
  - 1
    - Key: Authorization
    - Value: Bearer (JWT TOKEN)
  - 2
    - Key: Content-Type
    - Value: application/json
- Body: 
  -[
  
        {
            "messageId": (MESSAGE ID TO EDIT STATUS OF),
            
            "status" : (1 = SENT | 2 = DELIVERED | 3 = FAILED)
        },
        
        {
            "messageId": (MESSAGE ID TO EDIT STATUS OF),
            
            "status" : (1 = SENT | 2 = DELIVERED | 3 = FAILED)
        }
        
        ... YOU CAN HAVE ONE OR MANY MESSAGES IN THIS ARRAY
       
    ]

________________________________________________

Postman Collection
[Use Case 10 ](/RXMessengerAPI.docx)
________________________________________________

###### MessageDump API Request:

- Method: POST
- URL: https://localhost:5001/api/messaging/MessageDump
- Content-Type: application/json
- Headers: 
  - 1
    - Key: Authorization
    - Value: Bearer (JWT TOKEN)
  - 2
    - Key: Content-Type
    - Value: application/json
- Body: 
  -{
	
    "ClearMessages" : (0 = READ | 1 = REMOVE FROM QUEUE),
	
    "Hours" : (TIME IN HOURS TO READ/REMOVE)
    
   }

________________________________________________

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/e2eddd8c625f17286b24)
