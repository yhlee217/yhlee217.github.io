---
title: "20201210_Python&Excel"
date: 2020-12-10 04:50:57
updated: 2020-12-10 15:30:39
tags:
  - Python
  - Excel
---

## Python & Excel Basic

1. create_file.py
2. sheet.py
3. cell.py
4. open_file.py
5. cell_range.py

## 1 create_file.py

```
from openpyxl import Workbook
wb = Workbook() #새 워크북 생성
ws = wb.active # 현재 활성화된 Sheet 가져옴
ws.title = "TestWS" # sheet 의 이름을 변경
wb.save("Sample.xlsx")
wb.close
```

## 2. sheet.py

```
from openpyxl import Workbook
wb = Workbook() # 새 워크북 생성
ws = wb.create_sheet() # 새로운 Sheet를 기본 이름으로 생성
ws.sheet_properties.tabColor = "ff66ff" # RGB 형태로 값을 넣어주면 해당 시트의 색상을 변경
#Sheet, MySheet, YourSheet
ws1 = wb.create_sheet("YourSheet") # 주어진 이름으로 Sheet 생성
ws2 = wb.create_sheet("NewSheet", 2) # 2번 째 Index에 Sheet 생성
new_ws = wb["NewSheet"] # Dictionary 형태로 Sheet에 접근
print(wb.sheetnames) # 모든 Sheet 이름 출력
#Sheet 복사
new_ws["A1"] = "Test" # "A1"에 "Test 작성"
target = wb.copy_worksheet(new_ws)
target.title = "Copied Sheet"
wb.save("Sample.xlsx")
```

## 3. cell.py

```
from openpyxl import Workbook
wb = Workbook()
ws = wb.active
ws.title = "TestSheet"
#A1 셀에 1이라는 값을 입력
ws["A1"] = 1
ws["A2"] = 2
ws["A3"] = 3
ws["B1"] = 4
ws["B2"] = 5
ws["B3"] = 6
print(ws["A1"]) # A1 Cell의 '정보'를 출력
print(ws["A1"].value) # A1 Cell의 '값'을 출력
print(ws["A10"].value) # 값이 없을 때는 'None'을 출력
print(ws.cell(1, 1).value) # ws.cell(row, column).value
c = ws.cell(3, 1, 10) # ws["C1"].value = 10
print(c.value) #ws["C1"]
from random import *
#반복문을 이용해 랜덤 숫자 채우기
index = 0
for x in range(1, 11): # 10개 row
for y in range(1, 11): # 10개 Column
#ws.cell(x, y, randint(0, 100)) # 0 ~ 100 사이의 숫자
ws.cell(x, y, index) # 순서대로 기입
index += 1
wb.save("Sample.xlsx")
```

## 4. open_file.py

```
from openpyxl import load_workbook # 파일 불러오기
wb = load_workbook("Sample.xlsx") # sample.xlsx 파일에서 wb를 불러옴
ws = wb.active # 활성화된 Sheet
#cell 데이터 불러오기
for x in range(1, 11):
for y in range(1, 11):
print(ws.cell(row=x, column=y).value, end=" ") # 1 2 3 4 ..
print()
#cell 갯수를 모를 때
for x in range(1, ws.max_row + 1):
for y in range(1, ws.max_column + 1):
print(ws.cell(row=x, column=y).value, end=" ")
print()
```

## 5. cell_range.py

```
from openpyxl import Workbook
from random import *
wb = Workbook()
ws = wb.active
ws.append(["번호", "영어", "수학"]) #List
for i in range(1, 11): # 10개 데이터 넣기
ws.append([i, randint(70, 100), randint(70, 100)])
wb.save("Sample.xlsx")
```
