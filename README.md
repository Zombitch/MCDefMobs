# MCDefMobs

MCDefMobs is a behavior pack for Minecraft Bedrock version.
The purpose of this modification is to make hostile mobs neutral; this means they won't attack you except if you attack them first.
Exception for Nether where monster still hostile.

## How to install it ?

All along this instructions, I write about /data directory on the server that references in fact the /data directory of your minecraft installation.
_If you're using docker image, be advise to create a volume to mount data directory of minecraft docker container._

* Install npm on your computer
* Download this git repository and your local computer
* Run
> npm install --global yo generator-minecraft-addon

* On your computer, head to this project your just downloaded and run
> npm install
> npm run packageaddon

* This will create a .mcpack and .mcaddon inside the folder ./out/packaged/

* Transfert the .mcpack located on your local computer (./out/packaged) to your serveur in the data minecraft directory (ex : /data/behavior_packs/ )
* On your server, create a new folder for the behavior pack, for instance :
> mkdir /data/behavior_packs/MCDefMobs\ -\ MCDefMobs\ Behavior\ Pack/

* Unzip .mcpack inside that new directory
* Add the file "world_behavior_packs.json" in the following folder /data/worlds/YOUR_WORLD_NAME/ this file should contains something like this :[
>{
"pack_id" : "ffffac7b-bcc6-474c-a257-21aef6601778",
"version" : [ 1, 0, 0 ]
}
]

Above, it's really important to change pack_id value in order to match the uuid of your .mcpack header. You can find this information in the manifest.json file of the .mcpack.
Same instruction for the version value.
* Add the file "world_behavior_pack_history.json" in the following folder /data/worlds/YOUR_WORLD_NAME/ this file should contains something like this :
>{"packs":[{"can_be_redownloaded":false,"name":"MCDefMobs Behavior Pack","uuid":"ffffac7b-bcc6-474c-a257-21aef6601778","version":[1,0,0]}]}

Where name attribute has to be change to the name of your behavior pack folder created in step 2 and uuid and version should be change according to the same information as above (in step 4)
* Restart your server and play with this mod
