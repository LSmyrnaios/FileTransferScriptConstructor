# FileTransferScriptConstructor
A Python-program which constructs a transfer-SCP-script, based on given arguments.<br/>
The produced script, can contain commands to either transfer fromLocalToRemote or fromRemoteToLocal.<br/>

## How to run
Run with the following command:<br/>
``python fileTransferScriptConstructor.py -scriptFileFullPath <scriptFullPath> -hostsFileFullPath <hostsFullPath> -remoteUserName <userName> --wayOfTransfer -fromLocalToRemote/fromRemoteToLocal -localDir <localDir(only)Path> -remoteDir <remoteDir(only)Path> -generalFileName <fileToGetTransfered(withoutNums)> --isFileWithNum -True/False``<br/>

## Examples
You can check the functionality of **FileTransferScriptConstructor** by running these examples:<br/>

- Transfer **from local to remote**:
``python fileTransferScriptConstructor.py -scriptFileFullPath /home/user/scripts/localToRemoteFileTransferScript.sh -hostsFileFullPath exampleHosts.txt -remoteUserName root --wayOfTransfer -fromLocalToRemote -localDir home/user/filesToTransfer -remoteDir /home/user/ -generalFileName fileToTransfer.txt --isFileWithNum -False``<br/>
The output will be the script: "/home/user/scripts/localToRemoteFileTransferScript.sh", which will contain the following lines:<br/>
``scp /home/user/transferFiles/fileToTransfer.txt root@<IP-1>:/home/user/``<br/>
``scp /home/user/transferFiles/fileToTransfer.txt root@<IP-2>:/home/user/``<br/>
``scp /home/user/transferFiles/fileToTransfer.txt root@<IP-3>:/home/user/``<br/>
<br/>

- Transfer **from remote to local**:
``python fileTransferScriptConstructor.py -scriptFileFullPath /home/user/scripts/remoteToLocalFileTransferScript.sh -hostsFileFullPath exampleHosts.txt -remoteUserName root --wayOfTransfer -fromRemoteToLocal -localDir home/user/filesToTransfer -remoteDir /home/user/ -generalFileName fileToTransfer.txt --isFileWithNum -False``<br/>
The output will be the script: "/home/user/scripts/remoteToLocalFileTransferScript.sh", which will contain the following lines:<br/>
``scp root@<IP-1>:/home/user/ /home/user/transferFiles/fileToTransfer.txt``<br/>
``scp root@<IP-2>:/home/user/ /home/user/transferFiles/fileToTransfer.txt``<br/>
``scp root@<IP-3>:/home/user/ /home/user/transferFiles/fileToTransfer.txt``<br/>
