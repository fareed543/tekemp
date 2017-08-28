# tekemp
TekEMP - Java Spring Employee Management Application


How we created the Project :

Downloaded Eclips Version:Neon
 
Download Maven

Set Paths : 
M2_HOME : C:/maven Software /bin
PATH : C:/maven Software /bin

Error assembling WAR: webxml attribute is required (or pre-existing WEB-INF/web.xml if executing in update mode)

Fix this with below code :
<properties>
    <failOnMissingWebXml>false</failOnMissingWebXml>   
</properties>

Created Tables : 

create table employee(  id int(11) auto_increment primary key, first_name varchar(255), last_name varchar(255), dob date, image_name varchar(255), phone varchar(10), username varchar(255), email varchar(255), password varchar(255), address text )

create table employee_report( id int(11) references employee(id), report_date date, hours int(2), note text )

create table employee_leave( id int(11) references employee(id), leave_date date, subject varchar(255), message text )

create table employee_holiday( holiday_date date, holiday varchar(255) )
