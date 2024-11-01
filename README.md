#SCHEDULES PROJECT


## API 명세서

|기능|Method|URL|request header|response header|request|response_succes(2xx)|response_fail(4xx)|response_fail(5xx)|
|:----:|:----:|:----:|:----:|:--------:|:--------:|:--------:|:--------:|:--------:|
|일정 등록|POST|/api/schedule|Content-Type : application/json|Content-Type : application/json  Location :/schedule/{id}|“scheduleName” : “study”,  ”description” : “bootcamp”,  ”startPeriod” : “2024-09-30”,  ”endPeriod” : “2025-02-11”|201 Created  “id” : 1,  “scheduleName” : “study”,  ”description” : “bootcamp”,  ”startPeriod” : “2024-09-30”,  ”endPeriod” : “2025-02-11”|400 Bad Request  ”message” : “잘못된 요청입니다”|500 Internal Server Error  ”message” : “오류가 발생하여 요청을 수행 할 수 없습니다.”|
|일정 수정|PATCH|/api/schedule/{id}|Content-Type  : application/json||”description” : “nbcamp”|200 OK  “id” : 1,  “scheduleName” : “study”,  ”description” : “nbcamp”,  ”startPeriod” : “2024-09-30”,  ”endPeriod” : “2025-02-11”|400 Bad Request  ”message” : “잘못된 요청입니다”  404 Not Found  ”message” : “존재하지 않는 리소스입니다”|500 Internal Server Error  ”message” : “오류가 발생하여 요청을 수행 할 수 없습니다.”|
|일정 삭제|DELETE|/api/schedule/{id}||||200 OK  ”message” : “일정 삭제를 성공했습니다.”| 400 Bad Request  ”message” : “잘못된 요청입니다”  404 Not Found  ”message” : “존재하지 않는 리소스입니다”| 500 Internal Server Error  ”message” : “오류가 발생하여 요청을 수행 할 수 없습니다.”
|일정 조회|GET|/api/schedule||Content-Type: application/json||200 OK  “id” : 1,  “scheduleName” : “study”,  ”description” : “bootcamp”  ”startPeriod” : “2024-09-30”,  ”endPeriod” : “2025-02-11”| 400 Bad Request  ”message” : “잘못된 요청입니다”  404 Not Found  ”message” : “존재하지 않는 리소스입니다”| 500 Internal Server Error  ”message” : “오류가 발생하여 요청을 수행 할 수 없습니다.”
