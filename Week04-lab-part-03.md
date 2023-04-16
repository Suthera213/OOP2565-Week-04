# การทดลอง วาดไดอะแกรมด้วย plantUML (2)
## การวาดไดอะแกรมที่มีองค์ประกอบมากขึ้น

ให้นักศึกษาพิจารณาวาด uml diagram ของ code ต่อไปนี้ในกระดาษ โดยยังไม่ต้องใช้ plantuml จากนั้นให้ไปวาดใน  plantuml แล้วเปรียบเทียบผลที่ได้ว่าตรงตามที่คิดหรือไม่


1. 

``` plantuml
@startuml
"Football team" "1..1" *-- "12..20" "Player"
"Football team" "1..1" *-- "1..2" "Coach"
"Coach" - "Player": > teach
@enduml
```
![สมุดโน้ตไม่มีชื่อ-1](https://user-images.githubusercontent.com/115066359/232285653-2c1e68b9-1f33-49f8-bef3-e7a6cbf8364a.jpg)
![image](https://user-images.githubusercontent.com/115066359/232285694-6fabbf0d-217c-47ef-9f5b-ae9bf3860c8c.png)


2. 

``` plantuml
@startuml
class Student
{
  - name
  - ID
  - GPA
  + enrollSubject()
  + takeExamination()
}

class Subject
{
  - name
  - capacity
  - studytime
  + enrollStudent()
  + exam()
}

class Professor
{
  - name
  - emailAddress
  - instructs()
}

Student "10..40" - "0..1" Subject : > enrolled in
Subject "1" - "1..3 "Professor : < instructs
@enduml
```
![สมุดโน้ตไม่มีชื่อ-2](https://user-images.githubusercontent.com/115066359/232291363-54ed993f-8d2c-448a-8aaf-08df74be9f1e.jpg)
![image](https://user-images.githubusercontent.com/115066359/232291388-23a45e53-0c20-45ac-abc1-07dadda065eb.png)

3. 


``` plantuml
@startuml
class Clock
{
 - time
 + getTime()
 + incrementTime()
}

class Display
{
 - time
 + initTime()
 + setTime()
 + displayTime()
}

class HistoryCall
{
 - count
 + call()
 + answer()
} 

class Call
{
 - callDuration
 + getDuration()
} 

class OutgoingCall
{
  - number
  + Dial()
}

class IncomingCall
{
  - number
  + Answer()
}

MobilePhone "1" *-- "1" Clock
MobilePhone "1" *-- "1" Display
MobilePhone "1" *- "1" HistoryCall
HistoryCall "1" *-- "n" Call
Call <|-- IncomingCall
Call <|-- OutgoingCall
OutgoingCall "1" -- "1..12" DialPad : > use
IncomingCall "1" -- "1..2" AnswerButton : > use
DialPad -|> Keypad 
Keypad <|- AnswerButton
@enduml
```

![สมุดโน้ตไม่มีชื่อ-3](https://user-images.githubusercontent.com/115066359/232291405-6cba1c43-5bee-4c14-8981-3e43144a59c5.jpg)
![image](https://user-images.githubusercontent.com/115066359/232291415-a0e6131b-7b05-4e14-9cf4-60c620c74c38.png)



### จบการทดลองและแบบฝึกหัด
