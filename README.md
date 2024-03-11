# How to run

- Make sure Docker is installed and working on your system
- Clone the repository: `git clone git@github.com:rap4all/housing.git`
- Switch to the `docker` branch: `git checkout docker`
- Build the Docker image using `docker build -t housing_image .`
- Tag your image `docker tag housing_image angelfelizr/housing_image:0.0.99`
- Then we can remove the first image `docker rmi housing_image`
- Push the new image to dockerhub `docker push angelfelizr/housing_image:0.0.99` to be able to `pull` it later
- But another alternative is to save image and host it yourself `docker save angelfelizr/housing_image > housing_image.tar` to be loaded by calling `docker load < housing_image.tar`
- Run the Docker container (and mount a volume) using `docker run --rm --name housing_container -v /path/to/shared_folder:/home/housing/shared_folder:rw housing_image`
- Check the contents of `shared_folder` for the output.


