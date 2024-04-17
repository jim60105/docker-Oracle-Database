# Oracle Database on Docker + Backup

<section align="center">
  <p>
    <a href="https://github.com/jim60105/docker-Oracle-Database/blob/master/README.zh.md">
        Chinese
    </a>
    <span>| English</span>
  </p>
</section>

## Configuration

> If the backup location is in My Network Places, please use the CIFS branch.

1. Please refer to `*.env_sample` to create `*.env`
    - `SYS_PWD`: Your database SYS password
    - `CIFS_OPTION`: user=YOUR_CIFS_ACCOUNT,password=YOUR_CIFS_PASSWORD (this setting is for CIFS branch only)
    - `BACKUP_FOLDER`: The absolute path of the database synchronization directory, for example `D:\docker-Oracle-Database\backup`, `//192.168.0.1/backup`
1. Edit `docker-compose.yml`
    - If you want to backup, uncomment the backup service
    - If you want to restore, uncomment the restore service
1. `docker-compose up -d`

## Manual Backup and Restore

The backup and restore containers will stop after execution, just start the container to perform the operation.

- View the container name and start

  ```sh
  docker ps -a 
  docker start docker-oracle-database_backup_1
  docker start docker-oracle-database_restore_1
  ```

- Start from Windows Docker Desktop
![2021-06-21 11 53 10](https://user-images.githubusercontent.com/16995691/122706292-2d2a5180-d28a-11eb-823d-ef62172104f8.png)
