### Using your own editor while training on the remote and having the model file on local for visual inferece
The remote machine is set up with ubuntu server os, meaning no desktop environment. This makes it cruciating to quickly see what the trained RL agent learnt.

#### Some workarounds:
- log the run to wandb on the remote, and pull the saved model from the wandb run to your local machine.
>this got fucky for me, the model i pulled was not doing the same on local as on the remote

- mount the remote directory of puffer with `sshfs [user]@[host]:[remote-path] [local-mount-point]`
>i havent tried this one yet

- occasionally run rsync to push your local directory to the remote
>this can get messy bc it will push all the unwanted files too, like git blobs

- i wrote a quick script that only pushes files tracked under git to the remote with rsync, it has the same interface so flags like `-avzn` work as expected
> it gets tiresome to always push your changes. also, this still does not fix the problem of training on remote and getting the model on local

- the best thing i found is to push your local dir with the previous script to the remote, train the model on remote, pull only the `./experiments/` directory with rsync to have the model on local
>finally, this worked for me, i could edit the code with my prefered editor and the model trained on the remote worked as expected on the local machine
