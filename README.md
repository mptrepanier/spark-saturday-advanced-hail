### Spark Saturday Advanced - Hail 0.2 on Databricks

#### Instructions to Register for Free Databricks Community Edition

* Go to http://databricks.com/try-databricks
* Click on Get Started - Free
* Fill in the requested information and hit sign up. Ensure you use an email address that can access emails.

#### Instructions for Creating Hail Resource Libraries

The Hail resources necessary for running this tutorial are located in the resources folder. 

After downloading them, navigate to the Workspace/Users section of the notebook, and then to your user folder.

![1540412085592](C:\Users\micha\AppData\Local\Temp\1540412085592.png)

Within your user folder, right click and select create library.

![1540412271434](C:\Users\micha\AppData\Local\Temp\1540412271434.png)

On the next screen, create a library for the `hail-all-spark.jar` (name it whatever you want). Select the option to automatically have this library attached to all clusters (or manually attach it at a later point). Repeat the process for the `.egg` file. 

### Instructions for Creating a Cluster

Navigate to "Clusters" on the left-hand side of the screen and select "Create Cluster" on the top of the page that appears.

![1540412474468](C:\Users\micha\AppData\Local\Temp\1540412474468.png)

Name your cluster and then fill in the Spark Config like below.

![1540412601567](C:\Users\micha\AppData\Local\Temp\1540412601567.png)

```
spark.serializer org.apache.spark.serializer.KryoSerializer
spark.kryo.registrator is.hail.kryo.HailKryoRegistrator
spark.databricks.delta.preview.enabled true
spark.driver.extraClassPath ./hail-all-spark.jar
spark.executor.extraClassPath ./hail-all-spark.jar
```

Finally, click create cluster