## Cron job for auto backup database file

### create both shell in anywhere, I would like to create in /home directory

![image](https://user-images.githubusercontent.com/43438240/194832140-504edecd-1b2b-46a9-8f67-8446499c65a9.png)

## FULL day backup full.sh shell

    cd /var/opt/mssql/data/
    mv database_folder "/mnt/Full/file_name_$(date '+%HH-%MM-%d\%m\%Y')"

## Half of day backup half.sh shell
    cd /var/opt/mssql/data/
    mv database_folder "/mnt/Half/file_name_$(date '+%HH-%MM-%d\%m\%Y')"

## Update crontabe 
# BdBackup
    vim /etc/crontab
 ## Time format must be 24 hours utc+6
 
 10 2  * * *   root    /home/full.sh
 
 10 20  * * *   root    /home/half.sh

![image](https://user-images.githubusercontent.com/43438240/194831726-92cd4ded-24fc-47a9-b1be-79efb68f61b4.png)



