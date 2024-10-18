# picoCTF-2021-All-Event



**endianness** <code>General skill</code>

![Screenshot_2024-10-14_21_35_24](https://github.com/user-attachments/assets/57ce6f3b-8792-48ea-8c33-3429c83b611c)

* By using [CyberChef](https://gchq.github.io/CyberChef/#recipe=To_Hex('Space',0)Swap_endianness('Hex',4,true)From_Hex('Auto')Render_Image('Raw')) the file was put into the input section. Then converted to hex for the "Swap Endianness" function under a word length of 4. After this, the hex looks more like a JPG with the correct `ÿØÿà␀␐JFIF␀␁` magic bytes start. After the endianness was swapped and it's in the correct order it could be converted back from hex to get the data from the image. It could then be rendered in CyberChef to get the image that displays the flag.



**commitement issues**<code>General skill</code>

![Screenshot_2024-10-15_20_16_59](https://github.com/user-attachments/assets/2ce8488d-3853-4848-a78a-522d1de7ac9e)

* first download the zip file Then unzip challenge.zip.
* Then cd drop-in/ and with ls -a the ".git" file can now be seen. Originally there was just a file called "message.txt" with file contents "TOP SECRET". You can use the git log command to see prior commits made 

**Big zip**


![Screenshot_2024-10-15_20_35_21](https://github.com/user-attachments/assets/523ac687-10e6-4ca6-af64-c282a42ae252)


**first find**

![Screenshot_2024-10-15_20_52_35](https://github.com/user-attachments/assets/8846a7b4-bf2b-4668-ba28-a2ea186ba516)


**includes**

![Screenshot_2024-10-15_21_03_48](https://github.com/user-attachments/assets/63f01475-e3e5-49b0-b737-99be9d60e54d)

**pw crack 1**

![Screenshot_2024-10-15_21_49_46](https://github.com/user-attachments/assets/1ce2ab03-65a8-4307-be5a-4d8b1169505f)

**pw crack 2**

![Screenshot_2024-10-15_23_52_34](https://github.com/user-attachments/assets/8b360c82-af9f-4235-90f4-0fea69e135e3)

**information**

![Screenshot_2024-10-15_21_59_20](https://github.com/user-attachments/assets/6c3d2408-0adf-4974-983f-9589d47e644c)

**scan surpass** <code>forensics</code>


To get the file: wget https://artifacts.picoctf.net/c_atlas/3/challenge.zip, then unzip challenge.zip. Note: The files are also accessible with the provided ssh in the description. Use cd home/ctf-player/drop-in to get to flag.png.

Once there you can open the image and use a phone to scan the QR code and get the flag. Although it could also be done in Linux with zbar-tools.

**Binary search**<code>General skill</code>

![Screenshot_2024-10-13_20_33_52](https://github.com/user-attachments/assets/b73eef84-555b-4271-a03b-8b8e47bfddf3)

Welcome to the Binary Search Game!
* I'm thinking of a number between 1 and 1000.

* The first guess is going to always be 500 because it is the middle of 1 and 1000.

* For each guess after 500 the known lower bound is taken and the known higher bound is taken and divided by two for the next guess.

**Inspect html**

![Screenshot_2024-10-14_18_56_07](https://github.com/user-attachments/assets/2ff82198-7272-441d-ae90-4b446b0e3ca3)

* we have to enter to the wesite and right click .Then select inspect.go to html code and search for flag displayed there.


**Time machine**  <code>General skill</code>

![Screenshot_2024-10-14_16_45_41](https://github.com/user-attachments/assets/5c7e2919-815d-4f11-908e-b93f1bc88b4b)

* Its a general skill task.It contains a message.txt file in a zip file which as the CTF.allenge. For this challenge it is only needed to use the `git log` command where prior commits could be seen to have the flag displayed as a message attached to the git commit.

**Canyousee** <code>forensics</code>

![Screenshot_2024-10-14_20_59_36](https://github.com/user-attachments/assets/df81aed1-d616-4517-8ed2-e59179ae900f)

* This task comes under forensics. Actually forensics topic is intresting to solve .The flag is hiden in metadata.By running `exiftool ukn_reality.jpg` the Attribution URL section looks like it has Base64 encoded text (cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg==). By putting that text into [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)) with Base64 decoding the flag could be found.

* You could also get the flag in one command: `exiftool ukn_reality.jpg | grep At | cut -d ":" -f2 | tr -d " " | base64 -d`

The first part is getting the line of the Attribution URL section. Then use the cut command with the delimiter of a colon (:) and get the second field. Using the tr command to trim the leading spaces. Lastly, use `base64 -d` to decode the output and get the flag.

