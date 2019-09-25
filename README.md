# GoogleAssistantToVolumio
Use Google Assistant to controll Volumio

Google Assistant ---> IFTTT ---> Adafruit IO ---> python ---> Volumio

For this to work you need:
IFTTT account: https://ifttt.com
Adafruit account: https://io.adafruit.com
Something that runs Volumio, like a Raspberry Pi.

When logged in at Adafruit IO, go to Feeds, click Action, "Create new Feed". Call it whatever you want, I call mine "Volumio".  
Click Services, then IFTTT and connect, let it connect your Adafruit account to your IFTTT account.  
Click AIO Key on the right side, remember that information, it will be needed in the python script.  
Switch over to IFTTT and create a new applet, click your icon up in the right corner and choose Create.  
Click "This" in If This then That. In the search form type Google Assistant and click it. Choose "Say a phrase with a text ingredient".  
In "What do you want to say" you need to choose a specific keyword, I choose "Stereo". The keyword will be used like this for instance, "Hey Google, stereo ON".  
Write the keyword followed by a dollar sign, like "Stereo $" or "Speaker $", without the quotes.  
The following two textboxes are optional.  
The last box is also optional but I choose "$ sent to Volumio", that way if I say "Hey Google, stereo on" she will respond "On sent to Volumio" so I know she got the right command.  
Click "Create trigger".  
Click "That" in If Then That.  
Search for and choose Adafruit, click "Send data to Adafruit IO".  
If you have connected your accounts and made a Feed in Adafruit IO as described above you should see your feed under Feed name, so select it, Volumio in my case.  
Then click "Add ingredient", then TextField, then Create action.  
On the next page I like to deselect "Receive notification when this Applet runs", do as you want.  
Click Finish.  

Follow the instructions here https://adafruit-io-python-client.readthedocs.io/en/latest/index.html to install Adafruit IO.

You need to change a few things in the script.  
YOUR_AIO_USERNAME should be changed to your AIO Username from Adafruit IO.  
YOUR_AIO_KEY should be changed to your AIO Key from Adafruit IO.  
Also if you named your feed something other than Volumio you need to change "FEED_ID = 'Volumio'" as well.  
http://YOUR.IP.ADRESS.HERE should be changed to the ip of the Volumio machine, like http://192.168.1.19  
