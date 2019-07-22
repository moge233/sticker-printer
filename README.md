# sticker-printer
A propietary program written in Python used to print 2" x 1" and 1" x 1" stickers for automotive suspension parts.

# Disclaimer
** Due to my company's ownership rules, this program is not owned by me and therefore I cannot share the code in the program.  Instead, I will provide a description of the program along with screen shots of the program's GUI. **

# Background Information
At the automotive manufacture I work at, all assembled parts require a sticker label providing information regarding where in the factory the part was made (line and line group), what time it was made (year, month, day, hour, minute, seconds tens digit), and the part type identifier which is usually either a dash and a letter or two letters with one signifiying the model and one letter signifiying the hand (right/left).

Every part that is shipped out of our factory must have a sticker on it to identify the part.  This requirement even extends to pre-mass production parts, or new model parts as they are called.  An industrial printer (in our factory we use Intermec PD43's) is always part of the equipment setup used to produce parts.  Each process prints out one of these labels by having the PLC send the information to the printer.  The associate then places the label on the part, and finally they place the part in the machine to do what processes are needed to assemble the part.  Since the equipment used to produce new model parts is usually either still being built or the equipment is still being used to make a current mass production part (in the case of a model change), these labels must be printed by hand a lot of times.  At first, we were printing these stickers by sending the printer commands to a spare printer that we kept up in our open office.  This was a very tedious process.  Sometimes we would need up to 1000 stickers for pre-mass production event builds.  This meant we would have to send the printer commands and manually incrememnt all the time information in the sticker by hand.  It was very time consuming.  After doing this process by hand for months and months, I decided to look into writing a program to help us do this and also allow the non-engineering people in the office to print stickers on their own so the engineers wouldn't have to do it for them every time they needed stickers.  

# Sticker Descriptions
Depending on the part size, the customer will specify either a 2" x 1" sticker or a 1" x 1" label.  There is one type of 2x1 sticker and two 1x1 stickers.  The 2x1 sticker and one version of the 1x1 have similar layout and information.  These stickers contain the information previously described in the "Summary" section in both a human readable format 14 characters long.  This information is also coded inside a datamatrix that allows both our equipment to scan the label as well as the customer's equipment to scan the label to ensure that the part being shipped/received is the correct part.

The second version of the 1x1 label contains much less information than the first 1x1 label mentioned.  This sticker simply contains two letters describing the model and hand of the part.  These stickers do not contain any information regarding when and where the part was made.

One of these 3 stickers must be on every part that leaves our plant.

# Program Description
I decided that I was tired of doing this process by hand and wanted to write a program to do most of the work for me.  I ended up using Python because of its quick development time.  I found the *pyserial* library to help me send the commands to the printer using Python.  I also decided to write a GUI to go along with the program since I was the only person in the whole group with any Python experience.  I could have written instructions to allow others to use the program as a command line tool, but that would require them to know how to use the command line in the first place so I figured that the GUI would make it even easier for everyone else.  The end result was a GUI program that allowed the user to input pertinent information such as part type and hand, called a sticker layout from the printer's memory, sent variable information to the printer through a DB9-to-USB serial cable connected to the computer, automatically increased all time information, and printed an amount of stickers specified by the user.  Below are screen shots of the program in use.


![Screenshot 1](https://github.com/moge233/sticker-printer/screenshots/screenshot1.PNG)
![Screenshot 2](https://github.com/moge233/sticker-printer/screenshots/screenshot2.PNG)
![Screenshot 3](https://github.com/moge233/sticker-printer/screenshots/screenshot3.PNG)
![Screenshot 4](https://github.com/moge233/sticker-printer/screenshots/screenshot4.PNG)
