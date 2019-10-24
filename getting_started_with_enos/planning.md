# Unit 2: Initializing OU

Congratulations! Now you've logged into the EnOS Console. You can now initialize your OU to make it ready for your project, including OU profile and security settings, user and permission management, environment information, resource planning, and purchasing applications.

## Managing OU Profile and Security Settings

After logging in the EnOS Console with the administrator account, you can go to the **IAM > Organization Profile** page to edit the basic information of your OU and change your user name as needed. For more information, see [Managing the Organization Information and Organization Accounts](../iam/howto/managing_org_info_account).

To change the security settings for your organization, go to the **IAM > Security Setting** page and update the password policy, login IP restrictions, and session expiration time as needed. For more information, see [Setting the Security Options](../iam/howto/user/managing_security_settings).

## Managing Users and Permissions

To enable collaboration with multiple users, you can create 3 user account types, ordinary users (internal users within the OU), external users (imported from another OU), and LDAP users. To secure your assets and data, EnOS enforces access control of users:

- At the service level, so that a user would need to request proper access from the OU administrator to be able to read, write, or control objects in a service.
- At the asset level, so that a user can only access the assets that are authorized to the user.

Go to the **IAM > User** page to create user accounts and assign access permission for users. For information about how to manage users and user permissions, , see [Creating and Managing Users](../iam/howto/user/managing_users).

## Getting Environment Information

To connect your devices to EnOS through MQTT, consume the subscribed asset data, or invoke API service, you will need to get the environment information of EnOS.

The environment information of EnOS varies with the cloud region and instance where EnOS is deployed. Log in EnOS Console and go to **Help > Environment List** in the upper right corner to get the environment information.

## Planning Resource

Before you start your project on EnOS, you will first need to evaluate your volume of devices, data to be uploaded into EnOS, and the computing scale you need. This would help you determine how much computing and storage resource you will need to apply for to support your project.

Based on your business requirement, you can plan for the following resources:

.. list-table::
   :widths: 30 70

   * - Resource Name
     - Function Description
   * - Stream Analytics
     - The specification of the stream analytics computing resource is defined by the number of data points that can be processed every second. By evaluating your device and measuring point volume, you can decide how much computing resource you will need to apply for.
   * - TSDB
     - To store the data ingested from your devices for processing or further analysis, you need to apply for TSDB resource, which includes write resource and storage resource. Currently, only a standard specification can be applied for.
   * - Batch Computing
     - Computing capability for offline data analytics jobs. Batch computing resource can be requested based on computing unit (CU), with two kinds of computing specifications.
   * - Data Warehouse
     - A subject-oriented and integrated data storage environment for data analysis. Select the appropriate storage size according to actual business requirements (10 ~ 1,000G).
   * - Data Explorer
     - Before using the data explorer notebook to develop scripts for data processing and analysis, you will need to request the data explorer sandbox resource.
   * - File Storage HDFS
     - HDFS is used for big data analysis and storage scenarios. Select the appropriate storage size according to actual business requirements (10 ~ 1,000G).

For details about the computing and storage resource specification, see [Resource Specification](../resourcemanagement/reference.html).

## Next Unit

[Connecting and Managing Devices](device_connection)
