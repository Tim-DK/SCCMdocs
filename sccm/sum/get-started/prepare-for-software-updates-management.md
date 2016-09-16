

# Prepare for software updates management
Before the compliance assessment data of the software update displays in the System Center Configuration Manager console and before you can deploy software updates to client computers, you must complete the following steps: install and configure a software update point, synchronize the software updates metadata, and verify the configuration for settings that are associated with software updates.  

 When you have a Configuration Manager hierarchy, install and configure the software update point at the central administration site first, and then install and configure the software update points on other sites. Some settings are only available when you configure the software update point on the top-level site, which is the central administration site or the stand-alone primary site. There are different configuration options that you must consider depending on where the software update point is installed. Use the steps in the following table to install and configure the software update point, synchronize software updates, and configure the settings that are associated with software updates.  

 Use the following steps and procedures to prepare for software updates in Configuration Manager.  

|Step|Details|  
|----------|-------------|  
|[Step 1: Install and configure a software update point](install-a-software-update-point.md)|The software update point is required on the central administration site and on the primary sites to enable the software updates compliance assessment and to deploy software updates to clients. The software update point is optional on secondary sites.|  
|[Step 2: Synchronize Software Updates](synchronize-software-updates)|Choose your synchronization method depending on connectivity from the software update point to the update source:<br /><br /> <br /><br /> **Synchronize software updates from a connected software update point**<br /><br /> Software updates synchronization is the process of retrieving software updates metadata from the Microsoft Update site and the replication of the metadata to all sites that are enabled for software updates in the Configuration Manager hierarchy. The software update point on the central administration site or on a stand-alone primary site retrieves software updates metadata from Microsoft Update. The child primary sites and secondary sites retrieve the software updates metadata from the software update point that is identified as the upstream update source. You must have access to the upstream update source to successfully synchronize software updates. See [Synchronize software updates from a connected software update point](synchronize-software-updates-connected.md).<br /><br /> <br /><br /> **Synchronize software updates from a disconnected software update point**<br /><br /> Automatic synchronization of software updates is not possible when the software update point at the central administration site or stand-alone primary site is disconnected from the Internet. To retrieve the latest software updates for a disconnected software update point, you must use the WSUSUtil tool to export the software updates metadata and the license terms files from a software update source, and then you must import the metadata and files to the disconnected software update point.  See [Synchronize software updates from a disconnected software update point](synchronize-software-updates-disconnected.md).|  
|[Step 3: Configure classifications and products to synchronize](#BKMK_ConfigureClassesProducts)|Perform this configuration on the central administration site or stand-alone primary site.<br /><br /> After you synchronize software updates without any classifications or products selected, you must configure the software updates classifications and products in the Software Update Point Component properties. After you configure the properties, repeat step 2 to initiate the software updates synchronization to retrieve the software updates that meet the configured criteria for classification and products.|  
|[Step 4: Manage software updates settings](configure-software-updates-settings.md)|There are Configuration Manager client settings, group policy configurations, and software updates settings that you should verify and configure before you deploy software updates.|  