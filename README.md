# HP_SMART_APPX
This is .appX version of HP Smart tool version 115.1.152.0 without the email registration requirment.

The app will still attempt to automatically update itself and does not provide a 'dont update' option.
A firewall rule is required, to prevent the HP.Smart.exe from accessing the Internet. (This may break online functionality such as automated printer thumbnails or other online services)

1. Click the 'open printer app' link under the printer in windows 'Printers and Scanners'
0. Dont click 'update', simply leave it on screen for the moment
0. Open up task manager, go to the details tab and find the 'HP.Smart.exe' process
0. Right-click on the process and open file location
0. Select in the address field and copy the path
0. Open 'Windows Defender Firewall with Advanced Security'
0. Select 'outbound rule' on the left, then 'new rule' on the right
0. Select 'program' as the rule type and click next
0. Select 'This program path:' and paste the path copied from the proces file location explorer window, then click browse
0. Select HP.Smart.exe and click open, then next
0. Block a connection, next
0. Tick all boxes, Domain, Private, Public and next
0. Give it a name that you can find in the firewall list
0. Find the rule, right-click - properties
0. Select the scope tab, then under Remote IP address, select 'These IP addresses' and click add (Local IP address leave as any)
0. Select 'Internet' from 'Predefined set of computers' dropdown
0. Apply and OK
0. Now if you still have the HP Smart window open, with 'update', hit the X on the window
0. Check task manager, to confirm HP.Smart.exe is not listed, then click the 'open printer app'... should let you straight in.

Seems like a long list of steps, but its not that hard. A certificate instalation and developer mode may be needed for installation. In such cases:

1. Enable developer mode (Settings > Update & Security > For Developers)
0. Install the provided certificate or right-click the .appx > properties > digital signatures > certificate details > view certificate > install certificate
0. When installing certificate, it's best to install it local machine, and select Third-Party root certification authorities as a store.

After installation, you may disable the developer mode and remove the certificate from the store (look for  ED346674-0FA1-4272-85CE-3187C9C86E26). In my own experience, I had the app auto-updated via MS Store, but the firewall rule held and I was able to scan without the need for an account. Other online functionality in the app resulted in black pages.

(graciously copied and improved upon @sedstr's original. content encrypted to prevented automated takedowns - secret phrase: '*hpdumb*')