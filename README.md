# YT2Plex
Pull YouTube live streams into m3u playlist and xml guide for use with IPTV.  Configured for use with xteve on an unraid system, but this can be changed by editing the directories in main.py

# SETUP

1. Install xteve
  Can be found in community applications

2. Add scripts folder from YT2Plex to xsteve
  On unraid the directory where to add /scripts should look something like:
    /mnt/user/appdata/xteve

3. Edit main.py
  Add your API key to API_KEY
    Sign up for youtube data api at https://console.developers.google.com/apis
    API key can be generated under credentials tab
  Add/Remove Youtube channels you want
    Requirements:
     Youtube channel ID (obtain from https://www.streamweasels.com/tools/youtube-channel-id-and-user-id-convertor/)
     Channel Name (Name you want to appear in channel guide)
     Channel Icon (Link to image you want to appear in channel guide)

5. Install Python 3 on your system
  For Unraid systems:
    Install Nerd Tools from the community apps
    Open Nerd Tools
    Search for python
    Enable

6. Create a virtual enviroment for dependancies (Reccommended)
  In terminal:
     cd /path/to/your/directory

     pip3 install virtualenv

     virtualenv [Name of virtual env]

     source myenv/bin/activate

7. Install dependancies
   pip install google-api-python-client yt-dlp

8. Test
   Open Terminal
     /path/to/virtualenviroment/bin/python3 /path/to/xteve/scripts/main.py

   Verify playlist.m3u and guide.xml were created

9. Direct xteve to the new playlist and guide
   By default the xteve refers to its path as /root/.xteve so the path put into xteve should look like "/root/.xteve/scripts/playlist.m3u"

10. Map playlist and xmltv guide

11. Setup cronjob to run main.py however often you want to check the channels for live streams
