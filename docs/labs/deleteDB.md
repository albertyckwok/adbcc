# Delete an Autonomous Database
## Instroduction

After you finish all the labs, its important to clean up the environment so the next group has available resources. In this module you will terminate your Autonomous Database so the resources are released. In this example s database called **egtest** is terminated. You should **only** terminate the database your created and be careful not to terminate another groups database.

## Tasks:
1. From the **Database Console** page of your ADB service, click on your database.
    ![image1](images/2569dd9b76793a71fd87a1e43e54499f.png)
2. From the **Database Details** page of your ADB service, click on the **Actions** drop down 
    ![image2](images/a83f510a659e12ee9dc586b20469f1e2.png)
3. Select **Terminate** your service.
    ![image3](images/0635adb37c2f8f0a54ea7e8f35d2233b.png)
4. A **Terminate Autonomous Database** pop up appears, type in your  **Database Name** to confirm you want to delete it, then click **Terminate Database**
    ![image4](images/30d4b290e26c5fa7ac2fa919dd5fd826.png)
5. The Database Details console will reappear showing the database **Terminating**
    ![image5](images/64580f8cdfff174e081282b4641c7f99.png)
6. After a few minutes the database will show **Terminated**
    ![image6](images/7fe906e83809bb5acb1c76ab10ddac01.png)

In the Database Console page you will notice that the database remains in **Terminated** status. It takes about 24 hours for the database to dissapear from the Console, but it is no longer active or consuming resources.
![image7](images/826b82e32721429c43ebdb55c5bf2243.png)