create table department(id int primary key, name text);

create table employee(id int primary key, name text, salary int, departmentid int references department);

insert into department values (1, 'Management');
insert into department values (2, 'IT');

insert into employee values (1, 'John Smith', 30000, 1);
insert into employee values (2, 'Jane Doe', 50000, 1);
insert into employee values (3, 'Jack Jackson', 60000, 2);

create function GetEmployees() returns setof employee as 'select * from employee;' language 'sql';
