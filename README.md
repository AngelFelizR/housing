# How to run

- Getting the base folder
  - Make sure `Docker` and `Git` are installed and working on your system
  - Clone the repository: `git clone git@github.com:rap4all/housing.git`
  - Switch to the `docker` branch: `git checkout docker`

- Builing custom image
  - Build the Docker image using `docker build -t housing_image .`
  - Tag your image `docker tag housing_image angelfelizr/housing_image:0.0.99`
  - Now we can run the pipeline with the next comand `docker run --rm --name housing_container -v /c/Users/angel/R-folder/housing/output:/home/housing/shared_folder angelfelizr/housing_image:0.0.99`
  - Check the contents of `shared_folder` for the output

- Saving the the custom image
  - Push the new image to dockerhub `docker push angelfelizr/housing_image:0.0.99` to be able to `pull` it later
  - But another alternative is to save image and host it yourself `docker save angelfelizr/housing_image > housing_image.tar` to be loaded by calling `docker load < housing_image.tar`

- Finally, we can remove the first image `docker rmi housing_image`
