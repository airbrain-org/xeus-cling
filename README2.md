# Using the QuantStack xeus-cling Jupyter notebook
This notebook is runnable at mybinder.org: https://mybinder.org/v2/gh/QuantStack/xeus-cling/stable?filepath=notebooks/xcpp.ipynb

Unfortunately there does not appear to be a way to retain newly created notebooks or upload a previously created notebook. Another option is to run the same docker image in dockerhub:

```
docker pull gm5binder/binder-prod-quantstack-2dxeus-2dcling-2e3041:72a5f09789bbc2ad9e3464d46d619fb678d0ce93
```

# Running the QuantStack image

```
docker images

# Note the container ID of the newly downloaded image from the 'docker pull' command.

winpty docker run -it -p 8888:8888 {container ID}

```

# Saving a newly created notebook
The newly created notebook will be saved in ~/notebooks.  To retain this notebook within the docker 
container (from Windows, remove winpty for Ubunutu):

While running the QuantStack docker container, start another docker container and use the following command to commit your changes and save the notebook within the container:

```
docker ps

# Note the container ID of the running docker image.
# docker commit {container ID} {name of new image}, for example

docker commit 5199be5687e7 fp_presentation
```

# Verifying that the newly created notebook is present in ~/notebooks

```
winpty docker run -it {image name from above command, e.g. fp_presentation} bash
```
