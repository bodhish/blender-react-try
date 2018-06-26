# blender-farm
Objective is to create a software that could automatically spwan multiple render farms in Digital Ocean.

## The Process to create a render farm now

1, Create a Digital Ocean Account

2, Create a Cpu optimized Droplet

3, Connect to Droplet using SSH

4, Install Blender 2.79

Install Blender 2.79 via PPA

`sudo add-apt-repository ppa:thomas-schiex/blender`

Then upgrade Blender

`sudo apt-get update`

`sudo apt-get install blender`

5, Upload the blender file using scp

`scp [source file] [username]@[destination server]:.`

Replace the bracketed `[source file]`, `[username]` and `[destination server]` to match your local settings. So if the file was `test.blend` and your username on the remote sever is root and the destination sever is example.com, the command would be:

`scp test.blend root@example.com:.`

6, Render the file using the command

`blender -b file.blend -x blender -b file.blend -x 11 -o //render -a -o //render -a`

7, Download the file using scp

`scp [username]@[destination server]:[source file] [destination root]`

Replace the bracketed `[source file]`, `[username]` and `[destination server]` to match your local settings. So if the file was in the directory `/tmp/` and your username on the remote sever is root and the destination sever is example.com, the command would be:

`scp root@example.com:/tmp/*.png . `

8, Destroy the Droplet in digital ocean.



This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app).