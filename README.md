# pbs_qlist
A Uni-Bonn BAF-Cluster PBS qstat parser for Python3

Props to Oliver Evans and JLT for providing the basis of this program:
https://stackoverflow.com/questions/26104116/qstat-and-long-job-names

Takes the qstat -x output and parses it to a nicer and cleaner output.
Options are explained by qlist --help

How to get it working on your system:
1. Copy the qlist file to your local binary folder (e.g. ~/.local/bin).
2. Make shure the path is in your $PATH variable - if not do the following:
  Change your terminal profile to include the path, e.g. add 
  export PATH=~/.local/bin:$PATH
  to your
  ~/.bash_profile
  file (create one if it doesn't exist)
  
3. Change the path after #! to your Python3.X in the qlist file. If you are not sure where your Python sits, use:
  which python3
  You may have to plug in the command you use to open Python, but make sure it is version 3.0 or newer !!!

4. Make it executable via
  chmod +x qlist

5. You might want to restart the terminal session for bash to recognize the new command.

Tada! Now it should work.
Please note, that the command sometimes takes more time than expected and is usually slower than qstat itself.
I guess this is due to lustre performance problems, since the code is not CPU heavy at all.

# qint
With this bash command you can very easily start an interactive job on the same node as the job specified.
To use this program, basically repeat the same steps as for qlist but without the python part (since it is bash).

Usage: 

qint 142213116

Will start an interactive session requesting 1gb RAM and 5 mins walltime on the node that runs job 142213116.
Replace the number by any PBS session ID of your desire.
