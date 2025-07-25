# Create a freestyle job to run script.

So we are using jenkins here and freestyle job is one of service of jenkins and freestyle job is used to configure scripts and used to build docker images and push those images to their respective repository management and also used to deploy those on the server

In this repo we are going to see how to create a freestyle job and configure it and then build it. (the demo project we will be using it here is a java-maven-app)
[link for the project](https://github.com/Hemanth42d/java-maven-app-learning-jenkins.git)

1. The first and basic step is to install jenkins on the serve and can be done in two ways
  - Directly on os
  - Run as a docker service
  -If you haven't installed it then [check out this to install](https://github.com/Hemanth42d/install-jenkins-on-server.git)
2. After installation configure the jenkins like username password and all those steps

> create on + New item on the side bar of the jenkins dashboard
>   > give it a name > choose freestyle job > save
>   > click on configure in the sidebar of your job
>   > select for Git and provide the url, branch, credentials via ui
>   > if you want you can build and test it via maven
>   > By selecting **Invoke as top level maven** in Build steps dropdown 
>   > In Build Steps click on **Execute as shell** and now we can run shell commands in it
>   > ```bash
>   > chmod +x ./freestyle.build.sh
>   > ./freestyle.build.sh
>   > ```
>   > And then click on the save and after you will get into the page of your job and click on Build now in sidebar.

The things to remember is you need to have docker access inside the conatiner and node installed inside the conatiner and can be done via following command
```bash
sudo apt update
curl https://get.docker.com/ > dockerinstall && chmod +x dockerinstall && ./dockerinstall
ls -l /var/run/docker.sock # the file permisions needs to be change
chmod 666 /var/run/docker.sock

# node installation
curl -fsSL https://deb.nodesource.com/setup_20.x | bash -
apt install -y nodejs
node -v
npm -v
```
3. Now you are ready to Build and Test the application
4. And After the Build is successful you will get a success message if not you will get a failure message and can check what actually the failure is in the console log outputs.
