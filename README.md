[![magisk-manager.jpg](https://i.postimg.cc/L43JCvMJ/magisk-manager.jpg)](https://postimg.cc/t77R73Jb)
# Creating your first [Magisk](https://github.com/topjohnwu/Magisk/releases) module / [Создаём свой первый Magisk модуль - версия инструкции на русском](https://github.com/Andreyka445/Building-your-first-Magisk-module)  
# What are Magisk and ROOT managers?
Magisk is a tool that grants root privileges, while a Root manager is an application that controls who can use these privileges. In Magisk, these two functions are combined into a single package.

# Decide what we need the module for.
The most popular modules are those that edit system files, replace .prop variables, and execute all kinds of scripts.
Once we have decided what we need the module for, we move on to the next step—building the module.

# Contents
1) [What about Magisk and ROOT managers?](https://github.com/Andreyka445/Building-your-first-Magisk-module?tab=readme-ov-file#%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-magisk-%D0%B8-root-%D0%BC%D0%B5%D0%BD%D0%B5%D0%B4%D0%B6%D0%B5%D1%80%D1%8B-%D0%B2-%D1%86%D0%B5%D0%BB%D0%BE%D0%BC)
2) [Decide what we need the module for](https://github.com/Andreyka445/Building-your-first-Magisk-module?tab=readme-ov-file#%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B0%D1%87%D0%B0%D0%BB%D0%B0-%D0%BD%D1%83%D0%B6%D0%BD%D0%BE-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B8%D1%82%D1%81%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%87%D0%B5%D0%B3%D0%BE-%D0%BD%D0%B0%D0%BC-%D0%BD%D1%83%D0%B6%D0%B5%D0%BD-%D0%BC%D0%BE%D0%B4%D1%83%D0%BB%D1%8C)
3) [Build the module](https://github.com/Andreyka445/Building-your-first-Magisk-module#2-%D0%B2%D1%82%D0%BE%D1%80%D0%BE%D0%B9-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9---%D0%B7%D0%B0%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B8-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5--prop-%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D1%8B%D1%85)
4) [Replacing system files](https://github.com/Andreyka445/Building-your-first-Magisk-module#1-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F---%D0%B7%D0%B0%D0%BC%D0%B5%D0%BD%D0%B0-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%BD%D1%8B%D1%85-%D1%84%D0%B0%D0%B9%D0%BB%D0%BE%D0%B2)
5) [Replacing/Adding .prop variables](https://github.com/Andreyka445/Building-your-first-Magisk-module#2-%D0%B2%D1%82%D0%BE%D1%80%D0%BE%D0%B9-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9---%D0%B7%D0%B0%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B8-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5--prop-%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D1%8B%D1%85)
6) [Deleting system files/folders](https://github.com/Andreyka445/Building-your-first-Magisk-module#3-%D1%82%D1%80%D0%B5%D1%82%D0%B8%D0%B9-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9---%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D0%B8%D1%82%D0%B5%D0%BC%D0%BD%D1%8B%D1%85-%D1%84%D0%B0%D0%BB%D0%BE%D0%B9%D0%B2%D0%BF%D0%B0%D0%BF%D0%BE%D0%BA)
7) [Conclusion](https://github.com/Andreyka445/Building-your-first-Magisk-module#%D0%B7%D0%B0%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5)

# Module assembly
REQUIREMENTS: Magisk 20.4+
All config files must be in UTF-8 encoding. For convenient file editing, I recommend using [NotePad++](https://notepad-plus-plus.org/) / [MT-mangaer](https://mt-manager.net/)
The module must be in a .zip archive without password protection.

To begin assembling the module, download the “dummy file.”
1) Unzip the dummy file into any folder.
2) Make the necessary changes and assemble the finished module into a .zip file.

# Let's briefly go over each of the scenarios.

# 1) Usage scenario - Replacing system files.

  Replacing system files.
Inside the dummy file, there is a system folder. Place the files you want to replace in it, but make sure to keep the original file.


 You need to replace framework-res.apk, which is located in /system/framewrok.
 Solution: In the folder with the unpacked “dummy,” there is a folder called _system_. Create a folder called _framework_ in it and place your modified overlay there.

 What if the file you need to replace is in another section?

 If you need to replace a file in another partition, such as _/system_ext_, _/product_, or _/vendor_, it is IMPORTANT (bold) to create a folder with the desired partition, for example, _vendor_, inside the _system_ folder that is already in the dummy file, and specify the path to the file. It should look like this:     
 _/system/vendor/etc/hw/init.aee.rc_
 
 # 2) Second scenario - Replacing and adding .prop variables
   Required: Replace/Add .prop
   
   Solution: The downloaded dummy file contains a file called _sytem.prop_. Add your variable to it as it should appear in the system.

   Example: You need to disable blur, which is enabled by default in the system. To do this, copy the variables “ro.sf.blurs_are_expensive=1” and ro.surface_flinger.support_background_blur=1“ to the _system.prop_ file, where ”1" is _true (enabled)_ , and “0” is _false (disabled)_

   
   The final result in the _system.prop_ file looks like this: _“ro.sf.blurs_are_expensive=0” and ro.surface_flinger.support_background_blur=0"_
   
   # 3) Third scenario - Deleting system files/folders
  Task #1 -   Delete the system file

  Solution:

  ___Remember that the structure of files and folders must be identical to the system structure!___

  Let's go back to the first scenario, where we needed to replace framework-res.apk with our own, but now we will delete it.
  In the unpacked “dummy” in the _system_ folder, create a path _framework_, then create an empty .apk and name it  framework-res.apk, and place it in the path.

As a result, we got _system/framewrok/framewrok-res.apk (but our apk is already empty).

___Task #2 - Deleting a system folder/several directories at once___

Solution:
Let's look at an example using _system/fonts_

 In the folder with the unpacked “dummy” in the _system_ folder, create a folder called _fonts_. This will restore the original path to this folder within our module. Next, inside the folder, in my case _fonts_, create an empty file and name it “___.replace___.” 
 The final result is _/system/fonts/.replace_.

Flashing such a module will result in the complete deletion of all files in the directory.

If you need to delete several folders, you need to create a script ___customize.sh___, in which you write the following code, but replace the paths with your own

The structure of the deleted items must be identical to the system structure.
Important: If files/folders are deleted in separate system partitions “/vendor”, “/product” and (or) “/system_ext”, the path structure in the created module looks like this (placed inside “system”): “system/vendor/...”, “system/product/...”, “system/system_ext/...”. Do not create such directories in the root of your module!
Please note: Nothing is actually deleted from the system partitions! Everything will return to normal after the module is disabled/removed.

```
REPLACE="
/system/app/JamesDSPManager
/system/app/PrintSpooler
"
```
# Conclusion
___In conclusion, I would like to congratulate you on your first Magisk module!___
