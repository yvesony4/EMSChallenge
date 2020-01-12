# EMSChallenge
Employee Management System is a project to help manager record,edit,activate,suspend,delete an employee

this project has been done using Intellij IDEA and it's a full spring boot with Restful API
import it as a maven project in your IDEA and download dependencies in case you don't have them in your IDEA. After that you can run the project and
test with postman or anything familiar with you.

there are route which are in the challenge i followed to perform the following task

Saving employee
---------------
write the link: http://localhost:8080/employees with (REQUEST:POST) in your postman
then bypasse the employee details to the API by sending them as  either JSON or XML 
for example:    {
                 "employeeName": "karego",
                 "nationalId": "1199880044512077867890123456",
                 "phoneNumber": "+250787542156",
                 "email": "a6a@gmail.com",
                 "dateOfBirth": "1999-11-23",
                 "status": "inactive",
                 "position": "designer"
                 }
            
I have applied validation on data specified in the challenge  which includes: 
      1.  all the fields are required
      2.  National ID must be 16 digits
      3.  Email has to be valid with either gmail.com or yahoo.com
      4.  Phone number has to be valid and  rwandan(it means has to start with +250)
      5.  Employees below 18years old are not allowed
      6.  only active and inactive status allowed
      7.  only designer,developer,manager position allowed(they are enumerated)
      
Delete Employee
---------------
the delete works with nationalId.
in your postman use (REQUEST:delete) with the specified route in the challenge
example: http://localhost:8080/employees/1234867890123456 you will get a comfirmation message that that particular employeee is deleted in the system

Edit Employee
-------------
the system update based on nationald
in your postman use (REQUEST:put) with the specified route in the challenge
example: http://localhost:8080/employees/1234867890123456 you will need to edit in the body what you need to update and then send that JSON,XML you will then
check the response ans see that the field has been changed.

Activate Employee
-----------------
you activate an employee based on his nationalId
in your postman use (REQUEST:put) with the specified route in the challenge
example: http://localhost:8080/employees/1234867890123456/activate
this will change the status of an employee to active

Suspend Employee
----------------
you suspend an employee based on his nationalId
in your postman use (REQUEST:put) with the specified route in the challenge
example: http://localhost:8080/employees/1234867890123456/suspend
this will change the status of an employee to inactive


Search employee
---------------
you search an employee based on his position,email,phone number or Name
in your postman use (REQUEST:Get) with the specified route in the challenge
example: http://localhost:8080/employees/search/EmployeeName/NGABONZIZA : this is used for search by Name
         http://localhost:8080/employees/search/Email/yvesony4@gmail.com : this is used for search by email
         http://localhost:8080/employees/search/PhoneNumber/+250784021024 : this is used for search by Phone Number
         http://localhost:8080/employees/search/Position/designer : this is used for search by Position
