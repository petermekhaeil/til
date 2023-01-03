# Rename an AWS Lightsail instance

AWS Lightsail does not have an option to rename instances. However, you can create a new instance from a snapshot and give it the desired name. 

## Create a snapshot of the existing instance

1. From the Lightsail homepage, click on the name of the instance for which you want to rename.
2. Click on the **Snapshots** tab.
3. **Create snapshot** under the **Manual snapshots** section.

## Create new instance from the new snapshot

1. Choose the actions menu icon (⋮) next to the newly created manual snapshot.
2. Select **Create new instance**.
3. On the next page, enter the correct name.

## Attach existing static IP to the new instance

After verifying the new instance is running as expected, you may now re-attach the existing static IP.

1. From the Lightsail homepage, click on the name of the instance that is no longer needed.
2. **Stop** the instance.
3. Click on **Networking** tab.
4. **Detach** the static IP.
5. From the Lightsail homepage, select the newly created instance.
6. Click on **Networking** tab.
7. **Attach** the static IP to the new instance.

