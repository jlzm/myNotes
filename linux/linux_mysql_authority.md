<!--
 * @Author: jlzm
 * @Date: 2020-06-29 14:18:34
 * @LastEditors: jlzm
 * @LastEditTime: 2020-06-29 14:26:50
 * @FilePath: \myNotes\linux\linux_mysql_authority.md
--> 

# If you fail to connect to linux mysql database 
    Access denied for user 'root'@'localhost'
    
# You need to run the following steps
    sudo mysql -u root -p
    use mysql;
    select User, Host, plugin from user;;
    update user set plugin='mysql_native_password';
    fiush privileges;
    sudo service mysql restart