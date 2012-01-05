
# Folder Contents

The appliances folder contains mostly fragments of BoxGrinder configs (*.appl), which can be grouped together to create whole appliance definitions. Files beginning with "bg_" represent top-level definitions which can be used as input to BoxGrinder to create a fully functional appliance. All other *.appl files contain only partial config (fragments) and are missing important things such as disk sizes, operating system etc. These files are meant to be embedded into the "appliances:" section of other fragments or top-level appliance definitions.

Other directories include the "downloads" folder (explained below) and the "common_files" folder, which contains configuration files which will be included in the appliance definition by some fragments.

# Top Level Appliance Definitions

- bg_dev_drools: Java development tools and JBoss with Drools installed
- bg_dev_java: Java development tools (eg: Maven, Ant, Forge etc)
- bg_dev_mobicents: Java development tools plus Mobicents deployed on JBoss
- bg_dev_ruby_ee: Ruby development tools based on Enterprise Ruby
- bg_dev_tb_1: Java development tools with TorqueBox 1.x installed
- bg_dev_tb_2: Java development tools with TorqueBox 2.x installed
- bg_httpdha01: Active/passive failover Apache server, main node
- bg_httpdha02: Active/passive failover Apache server, slave node
- bg_jbilling_3: JBoss tools and JBilling 3 installed
- bg_mesabe: Mesabe installation (not yet working)
- bg_ruby_rmagick: Centos 5 + EPEL with custom compiled libraries required to get RMagick working with ImageMagick 6.5.7

# Setup

## Downloads

Some of these fragments use files which must first be downloaded from the interwebs. To do that, change into the "downloads" directory and execute the "download_files.sh" script. It will download everything from the "file_list.txt" file into that directory, which is where the fragments expect to find them.

## Private/Public Keys (optional)

None of the provided top-level appliances make use of the data_synchronisation fragment, but it is there to support any appliances which require passwordless SSH login between hosts (eg: for rsync). To allow this to work, just generate a id_dsa/id_dsa.pub key pair and place them in the "common_files" directory. Just don't upload them to GitHub, whatever you do! you may like to alter the data_synchronisation.appl file to change the location of the keys to be safer.

