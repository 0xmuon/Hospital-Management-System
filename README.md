# Hospital-Management-System
Class 12th ka fun
       
           PROJECT
     BACKGROUND

Nowadays there is a big trend of going digital and one of the best uses of this trend can be visualized in Hospital Management System where the track of numerous amount of paperwork required.

As there is much of paperwork, there is more chance of losing it in many ways like that in a fire, or misplacing some important files. So, the best use of Machines can be made in this case. 

Machines can store numerous large data on the disk and moreover just not storing, the data is safe. So if Hospital Management system go digital they can maintain a computer system that stores all the information of the Hospital management system like Booking Enquiry, Hospital enquiry, Appointment, Searching booking and there is still more which is beyond our imagination that machine can do.

In this program I took a little step forward by implementing the above in real life situation.


TECHNOLOGIES USED
Python Programming language
Python is an interpreted, high-level and general-purpose programming language. Python's design philosophy emphasizes code readability with its notable use of significant whitespace. Its language constructs and object-oriented approach aim to help programmers write clear, logical code for small and large-scale projects. 
Python interpreters are available for many operating systems. Python is a multi-paradigm programming language.  Many other paradigms are supported via extensions, including design by contract and logic programming. 

MySQL
MySQL Database Service is a fully managed database service to deploy cloud-native applications. HeatWave, an integrated, high-performance analytics engine accelerates MySQL performance by 400x.MySQL Cluster enables users to meet the database challenges of next generation web, cloud, and communications services with uncompromising scalability, uptime and agility.

SYSTEM REQUIREMENTS

Software Required:-
    MySQL 5.5 Command Line Client
Python 3.8
Microsoft Word for presentation of project.
Processors : x86 64-bit CPU ( INTEL/AMD )


Hardware Required:-

Operating systems:- Windows* 7 or later, macOS, and Linux.
Processor:- x86 64-bit CPU (Intel / AMD architecture)
RAM:- 2 Gb RAM or more.
Disk Space:-1 GB or more.



Objective of Project :-
To let the students apply the programming knowledge into a real- world situation/problem and exposed the students how programming skills helps in developing a good software.
Write programs utilizing modern software tools.
Apply object oriented programming principles effectively when developing small to medium sized projects.
Write effective procedural code to solve small to medium sized problems.




Module Definition :-
Patient Mode – 
This mode enables the user to deal with the Patient details. This helps to perform various tasks –


Adding Patient Details – This module adds the patient details by taking the sufficient information from the user .


Deleting Patient Details – This module deletes the patient record based on the suitable Patient ID.


Modifying Patient Details – This module modifies the  patient details.


Displaying Patient Details – This module displays the records of patient details by the user .
All patient details – This module displays all the records of patients.
For particular – This module displays for a particular patient details.


Doctor Mode –
 This mode enables the administrator to deal with the doctor details. This helps to perform several tasks –


Adding Doctor – This Module adds the doctor information.


Displaying Doctor Details– This module displays all the records of the doctor .
All Doctor details – This module displays all the records of doctors.
Status – This module displays that the doctor is available or busy.
Specialist – This module displays that the doctor is specialist .
Deleting Doctor – This module deletes the record of doctor with Doctor ID given by the user .


Modifying Doctor – This module modifies the doctor details .

 Payment Mode-
Online Mode-This module is defined for online payment.
Google Pay- This module is defined for online payment through google pay.
Debit Card- This module is defined for online payment through debit card.
Paytm- This module is defined for online payment through paytm.
Offline Mode- This module is defined for offline payment.
Cash- This module is defined for offline payment through cash.
Cheque- This module is defined for offline payment through cheque.




   Emergency Mode-
Ventilator Ambulance- This module defines ambulance with ventilator facility.
Basic Life Support Ambulance-This module defines ambulance for basic necessary AIDS.


 Report-
Hospital Information -This module will display the information about hospital.


Booking Bed - This module book the bed for the patient.


Room Information- This module displays information about the room.


Exit – It is used to close the program.
DESIGNING





Tables
Patient – 
                                                                 
                  
     Doctor-






Medicines –






Payment – 


Coding of the Program


import mysql.connector,random
from datetime import date
from subprocess import call
from sys import platform
mcon=mysql.connector.connect(host='localhost',user='root',passwd='quanta',database='HOSPITAL')
def clear():
    if platform not in ('win32', 'cygwin'):
        command = 'clear'
    else:
        command = 'cls'
    call(command, shell=True)
    
for i in range(0,5):
    print("\t\t\t\t\t\t\t\t\t\t","+ + "*2)
for j in range(0,4):
    print("\t\t\t\t\t\t\t\t"," "*3," ","+ + "*7)
for k in range(0,5):
    print("\t\t\t\t\t\t\t\t\t\t","+ + "*2)
def welcome():
    print("\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t========================= WELCOME TO AMBUJA VIDYA NIKETAN MEDICAL SCIENCES =========================")
    print("\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\t\t==================>>>  (1). PATIENT MODE     <<<==================")     
    print("\t\t\t\t\t\t==================>>>  (2). DOCTOR MODE      <<<==================")    
    print("\t\t\t\t\t\t==================>>>  (3). EMERGENCY        <<<==================")
    print("\t\t\t\t\t\t==================>>>  (4). REPORT           <<<==================")
    print("\t\t\t\t\t\t==================>>>  (5). EXIT             <<<==================")       
    print("\t\t\t\t\t\t--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--")
    print(" " *150)
    q=int(input("\t\t-->KINDLY,Enter your choice:-"))
    if q==1:
        patient()
    elif q==2:
        doctor()
    elif q==3:
        emergency()
    elif q==4:
        report()
    elif q==5:
        exit()
    else:
        print("\t\tOOPS!!you entered wrong number...PLEASE TRY AGAIN")
        print(" " *150)
        print(" " *150)
        welcome()
def patient():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t=============================== PATIENT  ================================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\t\t==================>>>  (1). ADD PATIENT DETAILS      <<<==================")
    print("\t\t\t\t\t\t==================>>>  (2). DELETE PATIENT DETAILS   <<<==================")    
    print("\t\t\t\t\t\t==================>>>  (3). MODIFY PATIENT DETAILS   <<<==================")
    print("\t\t\t\t\t\t==================>>>  (4). SHOW PATIENT DETAILS     <<<==================")
    print("\t\t\t\t\t\t==================>>>  (5). BACK                     <<<==================")       
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    a=int(input("\t\t-->KINDLY,Enter your choice:-"))
    if a==1:
        addpatient()
    elif a==2:
        delpatient()
    elif a==3:
        modpatient()
    elif a==4:
        showpatient()
    elif a==5:
        print(" " *150)
        print(" " *150)
        welcome()
    else:
        print("\t\tOOPS!!you entered wrong number...PLEASE TRY AGAIN.")
        patient()
        
def addpatient():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t======================= ADD NEW PATIENT DETAILS  ========================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t-->AMOUNGST THE FOLLOWING DOCTORS SELECT ANY OF YOUR CHOICE:")
    cur=mcon.cursor()
    cur.execute("select * from doctorDETAILS where STATUS='Available'")
    data=cur.fetchall()
    for row in data:
        print(row)
    print("\t\t\t\t\t\t==================>>>  (1). Dr.MANISH MEHTA        <<<===================")     
    print("\t\t\t\t\t\t==================>>>  (2). Dr.DHIRAJ JOSHI        <<<===================")    
    print("\t\t\t\t\t\t==================>>>  (3). Dr.NIKITA GANDHI       <<<===================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    l=int(input("\t\t-->KINDLY,Enter your choice:-"))
    if l==1:
        x=int(input("PATIENT ID:"))
        a=input("PATIENT NAME:")
        c=input("SEX:")
        d=int(input("AGE:"))
        e=input("DIAGNOSE:")
        f=input("ADDRESS:")
        g=int(input("CONTACT:"))
        h=input("DATE:")
        b="Dr.Manish Mehta"
        cur=mcon.cursor()
        cur.execute("insert into patientDETAILS values(%s,'%s','%s','%s',%s,'%s','%s',%s,'%s')"%(x,a,b,c,d,e,f,g,h))
        mcon.commit()
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t============  PLEASE VISIT Dr.Manish Mehta AT FLOOR 3 ===================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    elif l==2:
        x=int(input("PATIENT ID:"))
        a=input("PATIENT NAME:")
        c=input("SEX:")
        d=int(input("AGE:"))
        e=input("DIAGNOSE:")
        f=input("ADDRESS:")
        g=int(input("CONTACT:"))
        h=input("DATE:")
        b="Dr.Dhiraj Joshi"
        cur=mcon.cursor()
        cur.execute("insert into patientDETAILS values(%s,'%s','%s','%s',%s,'%s','%s','%s')"%(x,a,b,c,d,e,f,g,h))
        mcon.commit()
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t============  PLEASE VISIT Dr.Dhiraj Joshi AT FLOOR 8 ===================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")    
    elif l==3:
        x=int(input("PATIENT ID:"))
        a=input("PATIENT NAME:")
        c=input("SEX:")
        d=int(input("AGE:"))
        e=input("DIAGNOSE:")
        f=input("ADDRESS:")
        g=int(input("CONTACT:"))
        h=input("DATE:")
        b="Dr.Nikita Gandhi"
        cur=mcon.cursor()
        cur.execute("insert into patientDETAILS values(%s,'%s','%s','%s',%s,'%s','%s','%s')"%(x,a,b,c,d,e,f,g,h))
        mcon.commit()
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t============  PLEASE VISIT Dr.Nikita Gandhi AT FLOOR 8 ==================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")            
    else:
        print("\t\t-->OTHER DOCTORS ARE BUSY,KINDLY WAIT FOR SOMETIME!!!")
        print(" " *150)
        print(" " *150)
        welcome()
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t==========================BOOKING PROCESS DONE========================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t\t\t  IS THIS YOUR FIRST VISIT TO THIS HOSPITAL?   (yes/no)")
    h=input("\t\t-->KINDLY,Enter your choice:-")
    if h=="yes":
        print("\t\t-->YOUR ENTRY FEE IS RUPEES 300 ONLY/-:")
        print(" " *150)
        payment()
    else:
        print(" " *150)
        print(" " *150)
        patient()


def delpatient():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t======================== DELETE PATIENT DETAILS  ========================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    a=input("\t\t-->ENTER PATIENT ID:") 
    cur=mcon.cursor()
    cur.execute("delete from patientDETAILS where PatientID='%s'"%(a))
    mcon.commit()
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t=======================  PATIENT DETAILS DELETED  =========================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print(" " *150)
    welcome()
        
def modpatient():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t======================= MODIFY PATIENT DETAILS  =========================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\t\t====================>>>  (1). PATIENT NAME        <<<===================")     
    print("\t\t\t\t\t\t====================>>>  (2). REFFERED BY         <<<===================")    
    print("\t\t\t\t\t\t====================>>>  (3). AGE                 <<<===================")
    print("\t\t\t\t\t\t====================>>>  (4). DIAGNOSE            <<<===================")
    print("\t\t\t\t\t\t====================>>>  (5). CONTACT             <<<===================")
    print("\t\t\t\t\t\t====================>>>  (6). DATE                <<<===================")
    print("\t\t\t\t\t\t====================>>>  (7). BACK                <<<===================")
    print(" " *150)
    print("\t\tNOTE:- if you don't know the patient ID,then please press -->'0'<--(ZERO)**")
    a=int(input("\t\t-->KINDLY,Enter your choice:-"))
    if a==1:
        c=input("entre name:")
        b=int(input("\t\t-->ENTER Patient ID:"))
        cur=mcon.cursor()
        cur.execute("update patientDETAILS set Name='%s' where PatientID='%s'"%(c,b))
        mcon.commit()
    elif a==2:
        b=int(input("\t\t-->ENTER Patient ID:"))
        c=input("Reffered By")
        cur=mcon.cursor()
        cur.execute("update patientDETAILS set RefferedBy='%s' where PatientID='%s'"%(c,b))
        mcon.commit()
    elif a==3:
        b=int(input("\t\t-->ENTER Patient ID:"))
        c=int(input("Age"))
        cur=mcon.cursor()
        cur.execute("update patientDETAILS set Age='%s' where PatientID='%s'"%(c,b))
        mcon.commit()
    elif a==4:
        b=int(input("\t\t-->ENTER Patient ID:"))
        c=input("Diagnose")
        cur=mcon.cursor()
        cur.execute("update patientDETAILS set Diagnose='%s' where PatientID='%s'"%(c,b))
        mcon.commit()
    elif a==5:
        b=int(input("\t\t-->ENTER Patient ID:"))
        c=int(input("Contact"))
        cur=mcon.cursor()
        cur.execute("update patientDETAILS set Contact='%s' where PatientID='%s'"%(c,b))
        mcon.commit()
    elif a==6:
        b=int(input("\t\t-->ENTER Patient ID:"))
        c=input("Date:")
        cur=mcon.cursor()
        cur.execute("update patientDETAILS set Date='%s' where PatientID='%s'"%(c,b))
        mcon.commit()
    elif a==7:
        print(" " *150)
        print(" " *150)
        patient()
    elif a==0:
        cur=mcon.cursor()
        cur.execute("select PatientID,Name from patientDETAILS")
        data=cur.fetchall()
        for row in data:
            print(row)
        modpatient()
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t======================  PATIENT DETAILS MODIFIED  =======================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")        
    welcome()
def showpatient():
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t======================= SHOW  PATIENT DETAILS   =========================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print(" " *150)
        print("\t\t\t\t\t\t============>>> (1). FOR ALL PATIENT DETAILS          <<<================")
        print("\t\t\t\t\t\t============>>> (2). FOR A PERTICULAR PATIENT DETAIL  <<<================")
        print("\t\t\t\t\t\t============>>> (3). BACK                             <<<================")
        b=int(input("ENTER YOUR CHOICE:"))
        if b==1:
            cur=mcon.cursor()
            cur.execute("select * from patientDETAILS")
            data=cur.fetchall()
            for row in data:
                print(row)
        elif b==2:
            print("(1). IF YOU DO KNOW PATIENT ID")
            print("(2). IF YOU DON'T KNOW PATIENT ID")
            c=int(input("ENTER YOUR CHOICE:"))
            if c==1:
                    d=input("ENTER PATIENT ID:")
                    cur=mcon.cursor()
                    cur.execute("select * from patientDETAILS where PatientID='%s'"%(d))
                    data=cur.fetchall()
                    for row in data:
                        print(row)
            elif c==2:
                        cur=mcon.cursor()
                        cur.execute("select PatientID,Name,Diagnose from patientDETAILS")
                        data=cur.fetchall()
                        for row in data:
                            print(row)
                        d=int(input("ENTER PATIENT ID:"))
                        cur=mcon.cursor()
                        cur.execute("select * from patientDETAILS where PatientID=%s"%(d))
                        data=cur.fetchall()
                        for row in data:
                            print(row)
        else:
            
            patient()


def doctor():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t================================= DOCTOR ================================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\t\t==================>>>  (1). ADD DOCTOR DETAILS       <<<==================")
    print("\t\t\t\t\t\t==================>>>  (2). SHOW DOCTOR DETAILS      <<<==================")    
    print("\t\t\t\t\t\t==================>>>  (3). DELETE DOCTOR DETAILS    <<<==================")
    print("\t\t\t\t\t\t==================>>>  (4). MODIFY DOCTOR DETAILS    <<<==================")
    print("\t\t\t\t\t\t==================>>>  (5). MEDICINES                <<<==================")
    print("\t\t\t\t\t\t==================>>>  (6). BACK                     <<<==================")
    a=int(input("\t\t\t\t\t\t ENTER YOUR CHOICE:"))
    if a==1:
        adddoctor()
    elif a==2:
        showdoctor()
    elif a==3:
        deldoctor()
    elif a==4:
        moddoctor()
    elif a==5:
        medicine()
    elif a==56:
        print(" " *150)
        print(" " *150)
        welcome()
    else:
        print("\t\t TRY AGAIN!")
        doctor()
def adddoctor():
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t======================= ADD NEW DOCTOR DETAILS  =========================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print(" " *150)
        x=input("ID:")
        a=input("DOCTOR NAME:")
        b=input("POST:")
        c=input("SEPIACIALIST:")
        d=input("CONTACT :")
        e=input("STATUS:")
        f=input("DATE:")
        cur=mcon.cursor()
        cur.execute("insert into doctorDETAILS values(%s,'%s','%s','%s',%s,'%s','%s')"%(x,a,b,c,d,e,f))
        mcon.commit()
        print("\t\t\t\t-----------------------------+DONE+-----------------------------------")
def showdoctor():
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t======================= SHOW  DOCTOR DETAILS   =========================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print(" " *150)
        print("\t\t\t\t\t\t============>>> (1). FOR ALL DOCTOR DETAILS          <<<================")
        print("\t\t\t\t\t\t============>>> (2). FOR A PERTICULAR DOCTOR DETAIL  <<<================")
        print("\t\t\t\t\t\t============>>> (3). BACK                            <<<================")
        doc=int(input("\t\tENTER YOUR CHOICE:"))
        if doc==1:
            cur=mcon.cursor()
            cur.execute("select * from doctorDETAILS")
            data=cur.fetchall()
            for row in data:
                 print(row)
        elif doc==2:
            print("\t\t(1). -> DOCTORS AVAILABLE")
            print("\t\t(2). -> DOCTORS BUSY")
            c=int(input("\t\tENTER YOUR CHOICE:"))
            if c==1:
                print("\t\tA -> DOCTORS AVAILABLE")
                cur=mcon.cursor()
                cur.execute("select * from doctorDETAILS where STATUS='Available'")
                data=cur.fetchall()
                for row in data:
                    print(row)
            elif c==2:
                print("\t\t ->  DOCTORS BUSY")
                cur=mcon.cursor()
                cur.execute("select * from doctorDETAILS where STATUS='Busy'")
                data=cur.fetchall()
                for row in data:
                    print(row)
        elif doc==3:
                print("(1). ENT SPECIALIST")
                print("(2). HEART RELATED ISSUES")
                print("(3). ALLERGES")
                print("(4). EYE RELATED ISSUES")
                print("(5). SKIN RELATED ISSUES")
                c=int(input("ENTER YOUR CHOICE:"))
                if c==1:
                    cur=mcon.cursor()
                    cur.execute("select * from doctorDETAILS where SPECIALIST='ENT'")
                    data=cur.fetchall()
                    for row in data:
                        print(row)
                elif c==2:
                    cur=mcon.cursor()
                    cur.execute("select * from doctorDETAILS where SPECIALIST='CARDIOLOGIST'")
                    data=cur.fetchall()
                    for row in data:
                        print(row)
                elif c==3:
                    cur=mcon.cursor()
                    cur.execute("select * from doctorDETAILS where SPECIALIST='ALLERGIST'")
                    data=cur.fetchall()
                    for row in data:
                        print(row)
                elif c==4:
                    cur=mcon.cursor()
                    cur.execute("select * from doctorDETAILS where SPECIALIST='OPHTHALMOLOGIST'")
                    data=cur.fetchall()
                    for row in data:
                        print(row)
                elif c==5:
                    cur=mcon.cursor()
                    cur.execute("select * from doctorDETAILS where SPECIALIST='DERMATOLOGIST'")
                    data=cur.fetchall()
                    for row in data:
                        print(row)
            
                else:
                    print("THERE IS NO DOCTOR SPECIALIST IN:",c)


        welcome()
def deldoctor():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t======================== DELETE DOCTOR DETAILS  ========================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    a=input("\t\t-->ENTER ID:") 
    cur=mcon.cursor()
    cur.execute("delete from doctorDETAILS where ID='%s'"%(a))
    mcon.commit()
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t=======================  DOCTOR DETAILS DELETED  =========================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print(" " *150)
    welcome()
def moddoctor():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t======================= MODIFY DOCTOR DETAILS  =========================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\t\t====================>>>  (1). DOCTOR NAME        <<<===================")     
    print("\t\t\t\t\t\t====================>>>  (2). POST               <<<===================")    
    print("\t\t\t\t\t\t====================>>>  (3). SPECIALIST         <<<===================")
    print("\t\t\t\t\t\t====================>>>  (4). CONTACT            <<<===================")
    print("\t\t\t\t\t\t====================>>>  (5). STATUS             <<<===================")
    print("\t\t\t\t\t\t====================>>>  (6). DATE               <<<===================")
    print("\t\t\t\t\t\t====================>>>  (7). BACK               <<<===================")
    print(" " *150)
    print("\t\tNOTE:- if you don't know the ID,then please press -->'0'<--(ZERO)**")
    a=int(input("\t\t-->KINDLY,Enter your choice:-"))
    if a==1:
        c=input("Entre Name:")
        b=int(input("\t\t-->ENTER ID:"))
        cur=mcon.cursor()
        cur.execute("update doctorDETAILS set DOCTORname='%s' where ID='%s'"%(c,b))
        mcon.commit()
    elif a==2:
        c=input("Post:")
        b=int(input("\t\t-->ENTER ID:"))
        cur=mcon.cursor()
        cur.execute("update doctorDETAILS set POST='%s' where ID='%s'"%(c,b))
        mcon.commit()
    elif a==3:
        c=input("Specialist:")
        b=int(input("\t\t-->ENTER ID:"))
        cur=mcon.cursor()
        cur.execute("update doctorDETAILS set SPECIALIST='%s' where ID='%s'"%(c,b))
        mcon.commit()
    elif a==4:
        c=int(input("Contact:"))
        b=int(input("\t\t-->ENTER ID:"))
        cur=mcon.cursor()
        cur.execute("update doctorDETAILS set CONTACT='%s' where ID='%s'"%(c,b))
        mcon.commit()
    elif a==5:
        c=input("Status:")
        b=int(input("\t\t-->ENTER ID:"))
        cur=mcon.cursor()
        cur.execute("update doctorDETAILS set STATUS='%s' where ID='%s'"%(c,b))
        mcon.commit()
    elif a==6:
        c=input("Date:")
        b=int(input("\t\t-->ENTER ID:"))
        cur=mcon.cursor()
        cur.execute("update doctorDETAILS set DATE='%s' where ID='%s'"%(c,b))
        mcon.commit()
    elif a==7:
        print(" " *150)
        print(" " *150)
        doctor()
    elif a==0:
        cur=mcon.cursor()
        cur.execute("select ID,Name from doctorDETAILS")
        data=cur.fetchall()
        for row in data:
            print(row)
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t======================  DOCTOR DETAILS MODIFIED  =======================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")        
    welcome()
def medicine():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t=============================== MEDICINES  =============================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\tHERE IS THE LIST OF ALL THE MEDICIENS:")
    cur=mcon.cursor()
    cur.execute("select * from medicines"%())
    data=cur.fetchall()
    for row in data:
        print(row)
    a=int(input("\t\t\t\t\tENTRE SERIAL NUMBER OF MEDICINE YOU WANT TO ADD:"))
    if a<=5:
        cur=mcon.cursor()
        cur.execute("select * from medicines where SERIALNUMBER='%s'"%(a))
        data=cur.fetchall()
        for row in data:
            print(row)
        print("\t\t\t\t\t\t==================>>> (1). ADD MORE MEDICIENS  <<<===================")
        print("\t\t\t\t\t\t==================>>> (2). MEDICINES REQUIREMENT FULFILLED <<<=======")
        b=int(input("\t\tenter your choice:"))
        if b==1:
            medicine()
        else:
            print("\t\t\t\t\t\t============================== MEDICINES WILL BE DILIVERED TO PATIENT SHORTLY ==============================")
    else:
        print("\t\t\t\t\tHuh! MEDICINE NOT FOUND")
        print(" " *150)
        print(" " *150)
        doctor()
def payment():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t================================ PAYMENT  ===============================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\t\t=====================>>>  (1). ONLINE METHOD    <<<======================")
    print("\t\t\t\t\t\t=====================>>>  (2). OFFLINE METHOD   <<<======================")    
    print("\t\t\t\t\t\t=====================>>>  (3). BACK             <<<======================")      
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t CHOOSE ANY ONE METHOD YOU ARE SUITABLE WITH:")
    a=int(input("\t\t\t\t\t\t ENTER YOUR CHOICE:"))
    if a==1:
        print("\t\t\t\t\t\t G -> GOOGLE PAY")
        print("\t\t\t\t\t\t D -> DEBIT CARD")
        print("\t\t\t\t\t\t P -> PAYTM")
        b=input("\t\t\t\t\t\t ENTER YOUR CHOICE:")
        if b=="G" or b=="g":
            c=int(input("\t\t\t\t\t\t ENTER UPI:"))
            d=input("\t\t\t\t\t\t ARE YOU SURE ABOUT THE PAYMENT?     (yes/no)")
            if d=="yes":
                print("\t\t\t\t\t\t----------------+PAYMENT SUCCESSFUL+-----------------")
            else:
                print("\t\t\t\t\t\tPlease try again")
                billing()
        elif b=="D" or b=="d":
            e=int(input("\t\t\t\t\t\t CARD NUMBER:"))
            h=input("\t\t\t\t\t\t ENTER YOUR FULL NAME:")
            g=int(input("\t\t\t\t\t\t CVV:"))
            
            f=input("\t\t\t\t\t\t ARE YOU SURE ABOUT THE PAYMENT?     (yes/no)")
            if f=="yes":
                print("\t\t\t\t\t\t ----------------+PAYMENT SUCCESSFUL+-----------------")
            else:
                print("\t\t\t\t\t\t Please try again")
                billing()
        elif b=="P" or b=="p":
            print("\t\t\t\t\t\t PLEASE SCAN THE FOLLOWING CODE:")
            for i in range(1,10):
                for j in range (1,20):
                    symbol="*","|","~","!","-","+","^","#",":"
                    print(random.choice(symbol),end="")
                print("")
            k=input("\t\t\t\t\t\t HAVE YOU SCANNED THE CODE?     (yes/no)")
            if k=="yes":
                print("\t\t\t\t\t\t ----------------+PAYMENT SUCCESSFUL+-----------------")
            else:
                print("\t\t--> Please try again!!!")
                billing() 
            
    elif a==2:
        print("\t\t\t\t\t\t (1). CASH PAYMENT")
        print("\t\t\t\t\t\t (2). CHEQUE")
        l=int(input("\t\t\t\t\t\t ENTER YOUR CHOICE:"))
        if l==1:
            print("\t\t\t\t\t-----------+PAYMENT SUCCESSFUL+-----------")
        elif l==2:
            print("\t\t\t\t\t----------+PAYMENT SUCCESSFUL+----------- ")
    else:
        print("\t\t--> Please try again!!!")
    print(" " *150)
    print(" " *150)
def report():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t=============================== REPORT  ==============================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\t\t==================>>>  (1). HOSPITAL INFO    <<<=================")
    print("\t\t\t\t\t\t==================>>>  (2). BED INFO         <<<=================")    
    print("\t\t\t\t\t\t==================>>>  (3). ROOM INFO        <<<=================")      
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    a=int(input("\t\t-->KINDLY,Enter your choice:-"))
    if a==1:
        print("""All-India Institute of Medical Sciences was established as an institution of national importance by an Act of Parliament with the objects to develop patterns of teaching in Undergraduate and Post-graduate Medical Education in all its branches so as to demonstrate a high standard of Medical Education in India; to bring together in one place educational facilities of the highest order for the training of personnel in all important branches of health activity; and to attain self-sufficiency in Post-graduate Medical Education.
        The Institute has comprehensive facilities for teaching, research and patient-care.\t As provided in the Act, AVNMS conducts teaching programs in medical and para-medical courses both at undergraduate and postgraduate levels and awards its own degrees.\t Teaching and research are conducted in 42 disciplines. In the field of medical research AVNMS is the lead, having more than 600 research publications by its faculty and researchers in a year. AVNMS also runs a College of Nursing and trains students for B.Sc.(Hons.) Nursing post-certificate) degrees.""") 
    elif a==2:
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t=============================== BED BOOK  ===============================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t=====================>>>(1). Gatch Beds          <<<=====================")
        print("\t\t\t\t\t\t=====================>>>(2). Electric Beds       <<<=====================")
        print("\t\t\t\t\t\t=====================>>>(3). Low Beds            <<<=====================")
        print("\t\t\t\t\t\t=====================>>>(4). Air Mattresses      <<<=====================")
        print("\t\t\t\t\t\t=====================>>>(5). Fluidized-air Beds  <<<=====================")
        print("\t\t\t\t\t\t=====================>>>(6). ProBed Medical's 'Freedom Bed' <<<==========")
        a=int(input("\t\t-->KINDLY,Enter your choice:-"))
        if a==1:
            print("\t\t\t\t\t\t================>>> PAY RUPEES 150 PER DAY <<<=====================")
            payment()
        elif a==2:
             print("\t\t\t\t\t\t================>>> PAY RUPEES 200 PER DAY <<<=====================")
             payment()
        elif a==3:
             print("\t\t\t\t\t\t================>>> PAY RUPEES 1,500 PER DAY <<<=====================")
             payment()
        elif a==4:
            print("\t\t\t\t\t\t================>>> PAY RUPEES 1,000 PER DAY <<<=====================")
            payment()
        elif a==5:
             print("\t\t\t\t\t\t================>>> PAY RUPEES 3,000 PER DAY <<<=====================")
             payment()
        elif a==6:
             print("\t\t\t\t\t\t================>>> PAY RUPEES 5,000 PER DAY <<<=====================")
             payment()
        else:
            print("")
    elif a==3: 
        print("\t\t\t\t\t\t========================>>> (1). Twin Sharing Room <<<==============")
        print("\t\t\t\t\t\t========================>>> (2). Premium Twin Sharing Room <<<======")
        print("\t\t\t\t\t\t========================>>> (3). Deluxe Room <<<====================")
        print("\t\t\t\t\t\t========================>>> (4). Premium Deluxe <<<=================")
        print("\t\t\t\t\t\t========================>>> (5). Suite <<<==========================")
        print("\t\t\t\t\t\t========================>>> (6). Day Care <<<=======================")
        a=int(input("\t\t-->KINDLY,Enter your choice:-"))
        if a==1:      
            print("\t\t\t\t\t\t================>>> PAY RUPEES 500 PER DAY <<<=====================")
            print(" "*150)
            payment()           
        elif a==2:
            print("\t\t\t\t\t\t================>>> PAY RUPEES 1,000 PER DAY <<<=====================")
            print(" "*150)
            payment()
        elif a==3:
             print("\t\t\t\t\t\t================>>> PAY RUPEES 200 PER DAY <<<=====================")
             print(" "*150)
             payment()
        elif a==4:
             print("\t\t\t\t\t\t================>>> PAY RUPEES 550 PER DAY <<<=====================")
             print(" "*150)
             payment()
        elif a==5:
             print("\t\t\t\t\t\t================>>> PAY RUPEES 100 PER DAY <<<=====================")
             print(" "*150)
             payment()
        elif a==6:
             print("\t\t\t\t\t\t================>>> PAY RUPEES 250 PER DAY <<<=====================")
             print(" "*150)
             payment()
        else:
            print("\t\t  OOPS!!you entered wrong number...PLEASE TRY AGAIN.")
        emergency()
def emergency():
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print("\t\t\t\t\t\t=============================== EMERGENCY  ==============================")
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    print(" " *150)
    print("\t\t\t\t\t\t==================>>>  (1). VENTILATOR AMBULANCE     <<<=================")
    print("\t\t\t\t\t\t==================>>>  (2). Basic  Life  Support  Ambulance <<<==========")    
    print("\t\t\t\t\t\t==================>>>  (3). BACK                     <<<=================")      
    print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
    a=int(input("\t\t-->KINDLY,Enter your choice:-"))
    if a==1:
        ran=random.randint(1,199)
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t============ AMBULENCE NO.",ran," WILL BE REACHING YOU SOON.  ================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print(" " *150)
        print("\t\t\t\t\t\t================>>> PAY RUPEES 10,000 only /- <<<====================")
        payment()        
    elif a==2:
        ran=random.randint(1,199)
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")
        print("\t\t\t\t\t\t============ AMBULENCE NO.",ran," WILL BE REACHING YOU SOON.  ================")
        print("\t\t\t\t\t\t|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|")        
        print("\t\t\t\t\t\t================>>> PAY RUPEES 7,000 only /- <<<=====================")
        print(" "*150)
        payment()
    elif a==3:
        welcome()
    else:
        print("\t\t  OOPS!!you entered wrong number...PLEASE TRY AGAIN.")
        emergency()
    
def exit():
    print("\t\t\t\t=========================WE ENJOYED HELPING YOU!!=======================")
    print("\t\t\t\t\t=====================THANK_YOU========================")


welcome()
        
        
     




























     Output Screens
Home Screen-

1. Patient Mode-



Add Patient Details-

1.1.1.1 -   Pay through online google pay

1.1.1.2 - Pay through online debit card


1.1.1.3 - Pay through online Paytm

1.1.2.1-  Pay through offline Cash

1.1.2.2 - Pay through offline Cheque


1.2 Delete Patient Detail-

1.3.1 Modify patient details(Patient Name)-
1.3.2 Modify patient details (Referred by)-




1.3.3 Modify patient details (Age)-

1.3.4 Modify patient details (Diagnose)-

1.3.5 Modify patient details (Contact)-




1.3.6 Modify patient details (Date)-

1.4.1 Display all patient details-

1.4.2.1  Display particular patient details (if you do know Patient ID)-


1.4.2.2 Display particular patient details (if you don’t know Patient ID)-

Doctor mode –





Adding doctor details-


2.2.1Displaying All Doctor Details –


Displaying Particular  Doctor Details which is available -



Displaying Particular  Doctor Details which is busy –


Deleting Doctor details-


2.4.1 Modify Doctor Details (Name)-


2.4.2 Modify Doctor Details (Post)-


2.4.3 Modify Doctor Details (Specialist)-


2.4.4 Modify Doctor Details (Contact)-

2.4.5 Modify Doctor Details (Status)-


2.4.5 Modify Doctor Details (Date)-






Medicines –


Emergency-




Ventilator Ambulance-

3.1.1.1 -   Pay through online google pay

3.1.1.2 - Pay through online debit card



3.1.1.3 - Pay through online Paytm

3.1.2.1-  Pay through offline Cash

3.1.2.2 - Pay through offline Cheque


Basic  Life  Support  Ambulance-

3.2.1.1 -   Pay through online google pay

3.2.1.2 - Pay through online debit card


3.2.1.3 - Pay through online Paytm

3.2.2.1-  Pay through offline Cash

3.2.2.2 - Pay through offline Cheque


Report-

Hospital Info-

.1Bed Info(1)-



Bed Info (2)-

Bed Info(3)-

Bed Info(4)-




Bed Info (5)-

Bed Info (6)-

Room Info-




4.3.1 Room Info (1)-

Room Info(2)-

Room Info(3)-




Room Info(4)-

Room Info(5)-


Room Info(6)-



            TESTING
    TECHNOLOGIES 

White Box Testing
White-box testing (also known as clear box testing,
glass box testing, transparent box testing, and structural testing) is a method of testing software that tests
internal structures or workings of an application, as opposed to its functionality (i.e. black-box testing). In
white-box testing an internal perspective of the system,
as well as programming skills, are used to design test
cases. The tester chooses inputs to exercise paths through
the code and determine the appropriate outputs. This
is analogous to testing nodes in a circuit, e.g. in-circuit
testing (ICT). White-box testing can be applied at the
unit, integration and system levels of the software testing process. Although traditional testers tended to think
of white-box testing as being done at the unit level, it is
used for integration and system testing more frequently
today. It can test paths within a unit, paths between
units during integration, and between subsystems during
a system–level test. Though this method of test design can
uncover many errors or problems, it has the potential to
miss unimplemented parts of the specification or missing requirements.


Black Box Testing
Black-box testing is a method of software testing that
examines the functionality of an application without peering into its internal structures or workings. This method
of test can be applied virtually to every level of software
testing: unit, integration, system and acceptance. It typically comprises most if not all higher level testing, but
can also dominate unit testing as well. Specific knowledge of the application’s code/internal structure and programming knowledge in general is not required. The tester is aware of what the software is supposed to do but is not aware of how it does it. For instance, the tester is aware that a particular input returns
a certain, invariable output but is not aware of how the
software produces the output in the first place.
   BIBLIOGRAPHY 

Sites Referred:-
https://www.geeksforgeeks.org/
https://leetcode.com/
