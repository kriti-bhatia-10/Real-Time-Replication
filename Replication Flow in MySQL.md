
# Replication Flow (Process): How it happens in MySQL?


## Master Server:

The master server generates 'master log file'.

### Master Log File:
- Whenever something gets executed in the master server, for example someone executes an insert on the database in the master server, it gets logged into the master log file (also called binary log or binlog).
- The file names look something like this 'mysql-bin.000001','mysql-bin.000002' . The format of this file is binary, it's not human-readable. 
- The new binlog file gets created once the previous binlog  file reaches a certain size limit.

### Log Position:
- Log position is a position in a master log file which helps slave server to know where to start reading the data or bytes. 
- So let's say you execute some update statement in the database of a master server. It gets logged into master log file in the form of bytes. The log position helps the slave server to know from which point in the master log file it has to start reading. 
- The log position in master log file assists in tracking what changes have already been applied to the slave database in the slave server and which are yet to be applied.
- Example: The update statement change got logged into a master log file named 'mysql-bin.000002' at a specific position, let's say, '12345'. The slave will start reading from this position in master log file and applies the changes in its database.


## Slave Server:

The slave server connects to the master server and reads the 'master log file' and 'log position'.