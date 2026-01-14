# Get-RebootPersistence
NOTE: I HAVEN'T TOUCHED THIS IN A VERY LONG TIME AS CAN BE SEEN LOOKING AT THE LAST DATE I MADE ANY CHANGES
      THIS WAS WORKING AT ONE TIME BUT I HAD ONLY TESTED IT ON ONE PC SO THAT IS NOT EVEN MUCH OF A TEST
      I INTEND ON GETTING BACK TO THIS SOON
      THE ONE THING THAT I NEVER GOT AROUND TO TESTING WAS THE WEB BASED VERSION
      THAT I INTEND TO WORK ON AS WELL AT SOME POINT HOPEFULLY IN THE NEAR FUTURE AS I NEED TO GET BACK
      TO THIS KIND OF WORK AGAIN
      
Powershell script to maintain persistence after reboot

Still in alpha testing. I have used this method to start scripts post reboot on machines that do not have admin rights as login.

In this case as it is the script is designed to work as part of a social engineering attack. The user would be sent a script to run by an IT admin or some such thing and instructed to run it. The user would see activity in the terminal they may be familiar with and then prompted to either reboot or shutdown (only those two choices). 
While the script was showing the user some stuff on the screen the script would be writing files and a reg key to be ready to execute a reverse shell when the machine is rebooted.
Once the local listener picks up the shell from the target machine we will have system level access and will be able to do whatever we want including copy down the ZIP of files we both wrote and randomly copied phishing for easy info on the target including an ipconfig /all as well as copying the contents of the documents folder and the desktop of the logged in user.

This can (and I will create a version like this as soon as i can) be executed via an infected HTA webpage that the user is directed to visit.

In the end besides the initial access to the machine the goal is to mainain the access. Hiding the scripts which will execute silently via the \run regkey at boot time will ensure this. The only thing the attacker may need to do is obfuscate the reverse shell they choose to use via whatever is their fav method. Myself, I prefer to use Veil 
