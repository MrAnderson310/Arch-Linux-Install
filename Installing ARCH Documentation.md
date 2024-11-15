Before I could start the installation process there were a few things that I needed to do
1. Download the Arch iso file
2. Configure a new VM on UTM set up with Emulation

Set up the VM with 4 cores 4GB of RAM and 32GB of storage

Next Boot up the VM

Once the VM has spun up your cursor will be next to the line 

**root@archiso ~ #**

From this type "**archinstall**" 

You will next be met with a screen with a few options, the only ones to change are
 **Mirrors** - Change to United States
 **Disk Configuration** - Use the default partition layout, then use **btrfs** for easier rollbacks, and use compression
 **Root password** - Enter a strong password for the root account
 **User account** - create 3 different accounts, 1 for the default user, and 2 for justin and codi
**Network configuration** - **Choose Network Manager**
**Timezone** - Choose whatever time zone (CST most likely)

Then just press install and wait for it to do its thing

Next it will prompt you if you want to chroot into the new installation - Select YES

Then you will see **[root@archiso /]#**

Next Type **pacman -S gnome** to install the gnome desktop environment 

Then select your emoji fonts and hit Y to install

After it is done installing we need to exit so, type **exit** then **shutdown -h now** 

Next we need to remove the .iso file from the VM

To do this we go to UTM click on the Arch VM and click the settings button in the top right of the menu

A new menu will pop up, scroll on the left side until you see **IDE Drive** click on it then at the top it will show a Path with the ArchLinux iso file being referenced, **Click Clear**

Next Start back up the VM, it will show a screen that has the following: 
**ArchLinux login:**

Type the name of your user account, then the password associated with the user

Next we need to enable the gnome DM to do this type: **sudo systemctl enable gdm.service** 

Then enter your sudo password

Next we need to launch gnome and to do that type **sudo systemctl start gdm.service**

Then wait for it to load and now you have a GUI


**Installing ZSH**

Launch ArchLinux and login in as a user and open the terminal

To check which shell you currently have use the command **echo $SHELL**

Otherwise to install zsh type the command **sudo pacman -S zsh zsh-completions**

Then run zsh by typing **zsh** and then selecting **0**

To set zsh as your default shell you must use: **chsh -s /usr/bin/zsh**
\


Next is to change the theme of the zsh console

To do this we need to install a plugin called **ohmyzsh** 

To install it open up console and use the command sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

This will install ohmyzsh from here customize your console however you want using different themes or plugins


Adding Aliases

To add aliases we need to add some things to the zshrc file 

Type **vim .zshrc**

Press I to insert into vim

Then the format for any aliases is **"alias (thing you will type)="(The command you are replacing)**"

Then press esc and type "**:wq**" to save the file

Sit Back and admire your new arch Linux VM



