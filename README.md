# StashPlugins
A collection of python plugins for stash

### Currently available plugins:

Plugin config           | Description                                         | Notes
----------------------- | --------------------------------------------------- | --------
set_ph_urls.yml         | Add urls to pornhub scenes downloaded by Youtube-dl |
gallerytags.yml         | Copy information from attached scene to galleries   |
bulk_url_scraper.yml    | Bulk scene url scraping                             | Config (/py_plugins/config.py) has to be edited manually, until plugin parameters get implemented
update_image_titles.yml | Update all image titles (Fixes natural sort)        |
yt-dl_downloader.yml    | Download Videos automated with yt-dl and add the scrape tag for burl_url_scraper | Config files in yt-dl_downloader/ folder. Add all urls line by line to urls.txt and change download dir in config.ini |
    
### Download instructions:
Drop the py_plugins folder as well as all desired plugin configurations in stash's plugin folder
and press the `Reload plugins` button in the Plugin settings

All plugins require python 3, as well as the requests module, which can be installed with the command `pip install requests`.
If the python installation requires you to call python via `python3`, you have to change python to python3 in the exec block of each plugin config.


### Docker instructions:
To use the plugins with a stash instance running in a (remote-) docker container it is required to install python inside of it:
- Open a shell in the docker container: `docker exec -it <container-id> sh` (get the container id from `docker ps -a`)
- In the container execute the following commands:
    ```shell
    apt update
    apt install python3
    apt install python3-pip
    pip3 install requests
    ```
- Leave the container via `Ctrl+P,Ctrl+Q`
- Drop the py_plugins folder as well as all desired plugin configurations in stash's plugin folder located in `config/plugins`. Create the plugins folder if it is not already there
- Change `python` to `python3` in the plugin configuration (.yml) files
- Press the `Reload plugins` button in stash's plugin settings
