
NodeVersion
alejandro@alejandro-OptiPlex-3080:~/Documents/GitHub/conmed-dockerized$ node -v
v18.10.0
alejandro@alejandro-OptiPlex-3080:~/Documents/GitHub/conmed-dockerized$ npm -version
8.19.2


#POSTGRES 
sudo su postgres
cd /tmp
pg_dumpall > backupNew-10-13-2021

git add backupNew-10-13-2021
git commit -m ""
##in server final
sudo su postgres 
dropdb conmeddb02
psql conmeddb02 < backupNew-10-13-2021
psql -f backupNew-11-05-2021  postgres

#incrementals

sudo su postgres 
pg_dump --format plain --encoding UTF8 --schema-only  "conmeddb02" > /tmp/lala2

psql
\l  
\c conmeddb02 
 ALTER TABLE appointment_cancelled ADD COLUMN patient_confirmation integer, ADD COLUMN patient_confirmation_date timestamp with time zone ;

