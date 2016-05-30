Overview
========
This directory stores a default theme for an Open edX instance.

We've organized the tree to mimic the directory structure of the edX
codebase so that it's easy to tell where the files will end up upon
deploy. We'll use a special settings file to set the template and
staticfiles paths properly to point to these files.

![Alt text](/default_theme_screenshot.jpg?raw=true "Open edX Default Theme Screenshot")

Theme Authoring
===============
To customize your theme:
- Fork this repository.
- Clone it into the theme directory next to your edx-platform directory and rename the theme directory to your new theme's name.
- Upload your own image assets.
- Edit the .scss file in static/sass/ and rename the file with your theme's name.
- Edit the lms.envs.json file in edx-platform and set 'USE_CUSTOM_THEME' to true, and 'THEME_NAME' to your theme's name.


###Theme installation

Resources:

https://openedx.atlassian.net/wiki/plugins/servlet/mobile?contentId=60227913#content/view/60227913


```
sudo su edxapp -s /bin/bash
cd ~

source edxapp_env


cd /edx/app/edxapp/edx-platform

paver update_assets lms --settings=aws
```

```
exit

sudo /edx/bin/supervisorctl restart edxapp:
sudo /edx/bin/supervisorctl restart edxapp_worker:
```
