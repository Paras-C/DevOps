# READ ME

For Mac OS X 
1. To begin using this Project you will need to install Vagrant and Virtual Box.
2. Vagrant's latest download file can be found on their homepage:  ```https://www.vagrantup.com/```.
3. Virtual Box's download can be found on the following page (select the relevant operating system): ```https://www.virtualbox.org/wiki/Downloads```.
4. Run the respective PKG files to install them onto your machine.
5. Open Your terminal.
6. Check to see if vagrant has been installed by typing: ```vagrant```. If successful, a list of commands should appear. If not repeat steps 2 and 4.
7. Create a directory where ever you deem appropriate using: ```mkdir dev-environment```.
8. Change working directory to move into the previously created directory using: ```cd dev-environment```.
9. Clone the repository from GitHub using the command ```git clone git@github.com:Paras-C/DevOps.git```.
10. Ensure you are in the same directory as the vagrant file.
11. If so, in the terminal type ```vagrant up``` to start the virtual machine.
12. Once the loading has finished, type ```vagrant ssh``` to enter the virtual machines terminal.
13. Check to ensure you are in the virtual machines terminal and not the hosts.
14. Once in the VM's terminal, type ```cd app```.
15. Once in the app directory, run ```node app.js```.
16. Go to a browser on the host machine and navigate to ```development.local:3000```.




### Optional - To automate plugin installation
1. Open the vagrant file using ```subl .``` 
2. Type this at the top of the vagrant file: 
```
required_plugins = %w( vagrant-omnibus vagrant-aws )
required_plugins.each do |plugin|
    exec "vagrant plugin install #{plugin};vagrant #{ARGV.join(" ")}" unless Vagrant.has_plugin? plugin || ARGV[0] == 'plugin'
end
```
3. Change (within the brackets) the name of the plugin/s you require.
4. Save the file
5. ```vagrant up``` should now work automatically with plugins.


