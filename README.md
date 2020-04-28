# Installing Java, Maven and Springboot.

## Prerequisites
* Install vscode "code" command into your path. (If you don't have this. Or if you aren't sure follow this links guide)
    * https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line

## Java installation
We are going to install Java with a package manager called asdf and its plugins

### asdf install
* https://github.com/asdf-vm/asdf
    * Go to getting started at bottom of page.
* Make sure installation method is git. And clone only the latest branch.
* In the section named *_"Add to your Shell"_* make sure it's configured with
    * Operating system: macOS
    * Shell: zsh (if you're using it)
    * Installation Method: Git
* run ```code ~/.zshrc``` inside of your terminal and copy and paste this to the bottom of the file that just opened
```zsh
. $HOME/.asdf/asdf.sh
```
* Go back to your terminal and run ```source ~/.zshrc```
* Then run ```asdf --version```
    * You should seee an output similar to this ```v0.7.8-4a3e3d6```

Good job. We installed the asdf package into our machines! Now the next step is to install a plugin for asdf to handle java.

* Run this command ```brew install jq```
* Now go to these links and follow the installation instructions.
    * https://github.com/halcyon/asdf-java
    * https://github.com/skotchpine/asdf-maven

Now let us handle our java versions.
We want to tell our computer which version of java to install. We use a .tool-versions file in order to tell asdf which version to use
* ```touch ~/.tool-versions```
* Open the file with VSCode
* Paste in 
    1) ```java adopt-openjdk-8u222-b10``` on one line and 
    2) ```maven 3.6.3``` on another (in that order)
* Run ```code ~/.zshrc``` and at some point paste this in
    * ```export JAVA_HOME="$HOME/.asdf/installs/java/adopt-openjdk-8u222-b10"```
* Now run ```asdf install```
* And finally ```source ~/.zshrc```

Let us test out if we have both maven and java
* ```java -version```
* ```mvn --version```

### sdkman and springboot install
* Go to this link
    * https://sdkman.io/install
    * Note: if you're using zsh then run this command to install instead ```curl -s "https://get.sdkman.io" | zsh```
    * Run ```source "$HOME/.sdkman/bin/sdkman-init.sh"```
    * Run ```sdk version``` in your terminal to test if it was installed
* Now that you have it installed let us install springboot initiliazer cli
    * ```sdk install springboot```
    * Let us test spring boot
    * ```spring init spring-boot-monolith --dependencies=web --build=maven```
