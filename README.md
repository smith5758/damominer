# damominer
damominer for hiveos
If your mining machine has an ubuntu graphical interface, after the decompression is complete, you can directly start the operation from step 4. The following steps 1 to 3 are for the ubuntu command line version.

Before running DamoMiner, please make sure that your ubuntu system has successfully installed the graphics card driver! ! ! (The latest driver is not recommended)

1. Open the command box and use   sudo apt-get install wget  to install the wget tool.

2. After the installation is complete, use the command wget

https://github.com/damomine/aleominer/releases/download/damominer_linux_v2.0.0/damominer_linux_v2.0.0.tar , download DamoMiner running file.

(Note: If the domestic download is very slow, you can use wget https://ghproxy.com/https://github.com/damomine/aleominer/releases/download/damominer_linux_v2.0.0/damominer_linux_v2.0.0.tar  )

3. Use the command tar -xvf damominer_v2.0.0. tar to decompress and download to get the following files:



Among them, run_gpu.sh is the startup script of the GPU miner.

Add operation permission : 1. chmod +x damominer    2. chmod +x run_gpu.sh
Generate wallet command : ./damominer --new-account
4. Configure Aleo startup parameters:

1) Execute the command vi run_gpu.sh , the script demo is as follows:



 ./damominer  -- address aleo1rz3s5w2shzvmz0kcgppnxehuu4jvlps52nfqspfp9ck4ncekt5psfq68wv  --proxy aleo2.damominer.hk:9090

Note: The red part is the content that needs to be replaced

2) Modify the following content:
--address : add your own wallet address after the parameter 
--proxy : add the proxy address after the parameter: port ( aleo2.damominer.hk:9090/aleo3.damominer.hk:9090 )
--worker : parameter Change it to a custom miner name, example: --worker tester001 ( optional, if you don't fill in, you need to delete  --worker , the default is the intranet IP address )

5. After verifying that the filled information is correct, press the Esc key , enter : wq , save and exit, and execute the command  ./run_gpu.sh to start mining;

6. Tail -f aleo.log to check whether the log is normal.

7. After the correct deployment, you can see the relevant mining data after about half an hour.
