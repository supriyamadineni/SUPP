1st question
cd /opt
ls
cd nifi-2.7.2
cd bin
ls

sudo ./nifi.sh start

sudo ./nifi.sh set-single-user-credentials chitti uma1234567890

sudo ./nifi.sh restart

sudo ./nifi.sh status

mkdir -p /tmp/nifi_input
mkdir -p /tmp/nifi_output
mkdir -p /tmp/nifi_staging

cat > /tmp/nifi_input/students_raw.csv << 'EOF'
id,name,marks,department
1,ravi,85,CSE
2,anitha,90,ECE
3,ravi,85,CSE
4,kiran,45,ECE
EOF

ls /tmp/nifi_staging/
cat /tmp/nifi_staging/students_raw.csv
2nd one
# Start NiFi
cd /opt/nifi-2.7.2/bin
sudo ./nifi.sh start

# Create input and output directories
mkdir -p /tmp/nifi_input
mkdir -p /tmp/nifi_output

# Create sample CSV file
cat > /tmp/nifi_input/students.csv << 'EOF'
id,name,marks,department
1,ravi,85,CSE
2,anitha,90,ECE
3,kiran,75,CSE
4,meena,88,EEE
EOF

# Open NiFi UI
# http://localhost:8080/nifi

# ---- NiFi Flow Configuration ----

# Add Processor: GetFile
# Properties:
# Input Directory = /tmp/nifi_input

# Add Controller Service:
# CSVReader

# Add Controller Service:
# JsonRecordSetWriter

# Add Processor: ConvertRecord
# Properties:
# Record Reader = CSVReader
# Record Writer = JsonRecordSetWriter

# Add Processor: PutFile
# Properties:
# Directory = /tmp/nifi_output

# Connect:
# GetFile -> ConvertRecord -> PutFile

# Start all processors in NiFi UI

# ---- Check Output ----
ls /tmp/nifi_output
cat /tmp/nifi_output/students.json

# Check NiFi status
sudo ./nifi.sh status
3rd one
cd /opt/nifi-2.7.2/bin
sudo ./nifi.sh start

mkdir -p /tmp/nifi_input

cat > /tmp/nifi_input/students.csv << 'EOF'
id,name,marks,department
1,ravi,85,CSE
2,anitha,90,ECE
3,kiran,75,CSE
4,meena,88,EEE
EOF

sudo -u postgres psql
CREATE DATABASE college_db;
\c college_db
CREATE TABLE students (
id INT,
name TEXT,
marks INT,
department TEXT
);
\q

sudo ./nifi.sh status

sudo -u postgres psql -d college_db
SELECT * FROM students;
\q
4th
cd /opt/nifi-2.7.2/bin
sudo ./nifi.sh start

mkdir -p /tmp/nifi_input
mkdir -p /tmp/nifi_pass
mkdir -p /tmp/nifi_fail

cat > /tmp/nifi_input/students.csv << 'EOF'
id,name,marks,department
1,ravi,85,CSE
2,anitha,40,ECE
3,kiran,75,CSE
4,meena,30,EEE
EOF

sudo ./nifi.sh status

ls /tmp/nifi_input
ls /tmp/nifi_pass
ls /tmp/nifi_fail









sudo systemctl status postgresql

sudo systemctl start postgresql

sudo -i -u postgres psql

\l

alter user postgres with password 'root';

\q

sudo pgadmin4
