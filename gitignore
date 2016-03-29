

### data extraction using awk and get the text data into mysql database  
Create an sql from data file and upload it to SQL server. 
#### create a table called last in mysql service 
create table last(
      username VARCHAR(30),
      servicename VARCHAR(30),
      ipaddress VARCHAR(30),
      weekday VARCHAR(30),
      month VARCHAR(30),
      day INT NOT NULL,
      logintime VARCHAR(30),
      logouttime VARCHAR(30));
#### describe the data type in last table.      
describe last;   
#### go back to Unix shell and check the last data file 
last > last.txt 

cat last.txt | head -n 20
#### delete the bracket and change (00:00) to 00:00
cat last.txt | tr '( )' ' ' 
#### using awk to getting data into an analysis-ready form 
cat last.txt | awk -F ' ' '{print "INSERT INTO last(username,servicename,ipaddress,weekday,month,day,logintime,logouttime) VALUES (\x27"$1"\x27,\x27"$2"\x27,\x27"$3"\x27,\x27"$4"\x27,\x27"$5"\x27,\x27"$6"\x27,\x27"$7"\x27,\x27"$8,$9,$10"\x27);"}' >myresult.sql 
####carry out the myresult.sql in mysql database 
mysql -u ymzhang2 -p ymzhangdb <myresult.sql> ### where ymzhang2 is the username and ymzhang2db is the database name) 
#### go back to my mysql database
mysql -u ymzhang2 -p 
use ymzhang2db;
select * from last; ## check all the insert rows 
