# KillerBee
This is a tool for visualizing the results of Blind SQL Injection
This tool may help you to gather the important informations(schema, table, column, etc..) and actual data that stored in database.
Please use it for legitimate Vulnerability Pentesting to your Website

anstjddbs12@gmail.com / @Moonster8282

**MSSQL VERSION HAS NOT BEEN CODED YET**

# Version
1.0

# Dependencies
KillerBee requires Python 3.9 and the following modules:
* openpyxl
* asyncio
* aiohttp
* tkinter
* pandas
* numpy

You can just install following modules:
```
pip install --upgrade pip
pip install -r requirements.txt
```

# Usage
* **Step 1.** Clone this to ```/anywhere/you/want```
```
git clone https://github.com/Moonster8282/KillerBee
```

* **Step 2.** Edit following default settings on code:
```
...
#A. Set Your Database Type: 1 = Oracle, 2 = Mysql, 3 = Mssql
database_type = 2
DATA_MAX_COUNT = 1000000 # update this value if data tuples expected over 1,000,000 ex. 10000000 or 100000000
...

...
#B. The value that can be determined when the query results are true
delims="1234-5678-2300-9000"
...

...
#C. Vulnerable point's method, data parse type, url, header, cookie
method = {get|post}
data_types = {form|json}
header_raw = """
HEADER CONTENTS
"""
cookie_raw = """
COOKIE CONTENTS
"""
...

...
#D. Vulnerable point's Parameters and Value
# you should always contain `{query} between {mid+1} and {max}`
params = {
    "uname":"admin",
    "pass": f"' or {query} between {mid+1} and {max}--'"
}
...

...
#E. Type your project foler name
e_name.insert(0, "THIS_IS_FOLDER_NAME")
...
``` 

* **Step 3.** Now you can excute with following commands:
```
python3 ./injecter.py
```

# Example
## How to Start
**Top Menu Bar -> Injection -> 테이블 인젝션 시작** : Gather Schema Informations(Table counts, Table name, Data counts)
![image](https://github.com/user-attachments/assets/2b48f646-75e6-4d94-8d4e-cfb71a797b50)

## How to load exist work

**Top Menu Bar -> Injection -> 테이블 인젝션 시작**
```
Y : load existing work
N : reset existing work and gathering start
취소 : cancel
```
![image](https://github.com/user-attachments/assets/83c5126b-c4c7-4099-89e7-19b60890cc55)


* Other Options
```
Top Menu Bar -> Injection -> 테이블 인젝션 중지 : Stop Gather Schema Informations
Top Menu Bar -> Injection -> 컬럼 인젝션 시작 : Add Column gather job for every table and starts immediately
Top Menu Bar -> Injection -> 컬럼 인젝션 중지 : Stop Column gather job
Top Menu Bar -> Injection -> 데이터 인젝션 시작 : Add Data gather job for every table and starts immediately
Top Menu Bar -> Injection -> 데이터 인젝션 중지 : Stop Data gather job

Top Menu Bar -> Action -> 모든 컬럼 작업에 추가 : Add Column gather job for every table
Top Menu Bar -> Action -> 모든 데이터 작업에 추가 :  Add Data gather job for every table
```

## How to check column or data 

**point table name(테이블 이름) and click mouse middle button** : load table's existing column or data
![image](https://github.com/user-attachments/assets/e7b91590-1e91-49c8-a2f5-9f616bb0b6b5)

if you already collected data, it will be appeared like this:
![image](https://github.com/user-attachments/assets/98e79c79-9225-4f64-9af0-b92cd6e16bf6)

## How to Add Simple job to job table

**point column status(컬럼 수집) and click mouse middle button** : Add Column gather job to job table(when Value is `X`)
![image](https://github.com/user-attachments/assets/cd33d0e3-1369-424d-9d9c-6c571545d4a7)

**point data status(데이터 수집) and click mouse middle button** : Add Data gather job to job table
![image](https://github.com/user-attachments/assets/5f3f20d5-2afb-482f-860e-6dd4c07f584f)

## How to Control Job Table
```
1. 시작 : start job
2. 정지 : stop job
3. 삭제 : delete selected job
4. 최상위로 : sets the selected job to the top
5. 위로 : sets the selected job to the upper
6. 아래로 : sets the selected job to the lower
7. 작업 초기화 : reset all the jobs
```
![image](https://github.com/user-attachments/assets/e4650b94-86c1-4ec3-94c9-f85f5be2e237)
