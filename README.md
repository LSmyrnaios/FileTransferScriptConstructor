TransferScriptConstructor
=========================

A Python-program which constructs a transfer-SCP-script, based on given arguments.<br/>
The produced script, can contain commands to either transfer fromLocalToRemote or fromRemoteToLocal.<br/>

Run command:<br/>
``python TransferScriptConstructor.py -scriptFileFullPath <scriptFullPath> -hostsFileFullPath <hostsFullPath> -remoteUserName <userName> --wayOfTransfer -fromLocalToRemote/fromRemoteToLocal -localDir <localDir(only)Path> -remoteDir <remoteDir(only)Path> -generalFileName <fileToGetTransfered(withoutNums)> --isFileWithNum -True/False``<br/>

Examples
--------
You can check the functionality of **TransferScriptConstructor** by running these examples:<br/>

- Transfer from local to remote:
``python TransferScriptConstructor.py -scriptFileFullPath /home/user/scripts/localToRemoteTransferScript.sh -hostsFileFullPath exampleHosts.txt -remoteUserName root --wayOfTransfer -fromLocalToRemote -localDir home/user/filesToTransfer -remoteDir /home/user/ -generalFileName fileToTransfer.txt --isFileWithNum -False``<br/>
The output will be the script: "/home/user/scripts/localToRemoteTransferScript.sh", which will contain the following lines:<br/>
``scp /home/user/transferFiles/fileToTransfer.txt root@<IP-1>:/home/user/``<br/>
``scp /home/user/transferFiles/fileToTransfer.txt root@<IP-2>:/home/user/``<br/>
``scp /home/user/transferFiles/fileToTransfer.txt root@<IP-3>:/home/user/``<br/>
<br/>

- Transfer from remote to local:
``python TransferScriptConstructor.py -scriptFileFullPath /home/user/scripts/remoteToLocalTransferScript.sh -hostsFileFullPath exampleHosts.txt -remoteUserName root --wayOfTransfer -fromRemoteToLocal -localDir home/user/filesToTransfer -remoteDir /home/user/ -generalFileName fileToTransfer.txt --isFileWithNum -False``<br/>
The output will be the script: "/home/user/scripts/remoteToLocalTransferScript.sh", which will contain the following lines:<br/>
``scp root@<IP-1>:/home/user/ /home/user/transferFiles/fileToTransfer.txt``<br/>
``scp root@<IP-2>:/home/user/ /home/user/transferFiles/fileToTransfer.txt``<br/>
``scp root@<IP-3>:/home/user/ /home/user/transferFiles/fileToTransfer.txt``<br/>
