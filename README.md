# MessengerWebAPI


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
[Use Case 6 / 8 / 10](/RXMessengerAPI.docx)
________________________________________________

###### Use Case 6

Test API Request:

- Method: GET
- URL: https://localhost:5001/api/messaging/Test
- Content-Type: application/json
- Headers: 
  -Key: Authorization
  -Value: Bearer (FOLLOWED BY JWT TOKEN WITHOUT BRACKETS)
- Body: none


GetBatch API Request:

- Method: POST
- URL: https://localhost:5001/api/messaging/AckBatch
- Content-Type: application/json
- Headers: 
  -Key: Authorization
  -Value: Bearer (FOLLOWED BY JWT TOKEN WITHOUT BRACKETS)
- Body: none


AckBatch API Request:

- Method: POST
- URL: https://localhost:5001/api/messaging/GetBatch
- Content-Type: application/json
- Headers: 
  -Key: Authorization
  -Value: Bearer (JWT TOKEN)
- Body: 
  - {
  
      "batchId": (BATCH ID RETURNED FROM GetBatch),
      
      "batchMessageCount": (BATCH MESSAGE COUNT RETURNED FROM GetBatch),
      
      "batchNote": ("BATCH NOTE IF ANY")
      
    }



###### Use Case 8

EditMsgStatus API Request:

- Method: POST
- URL: https://localhost:5001/api/messaging/EditMsgStatus
- Content-Type: application/json
- Headers: 
  -Key: Authorization
  -Value: Bearer (JWT TOKEN)
- Body: 
  -[
        {
            "messageId": 1,
            
            "status" : 0
        },
        
        {
            "messageId": 2,
            
            "status" : 1
        }
    ]


[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/e2eddd8c625f17286b24)
