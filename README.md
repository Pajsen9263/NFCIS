# NFCIS
NFCIS is a inventory system using the NFCDBI principle. It makes use of a Raspberry Pi, Raspberry Pi Screen, NFC reader and a Database (currently only SQL).  

NFCIS is designed for the Raspberry pi (with a touchscreen and NFC reader) so it can be cheap and easy to use. The project is aimed for schools to keep track of what student has what book. For the first physical prototype we used a 3D printed case (custom made). The physical prototype has gotten the name NFCIS Vault (see bellow). 

## IC 
The Interface Core is the base level API that is needed for the SUI and SAGI to work. It provides the direct interface with the Maingateway and a front end client. You could remove the IC but that means you have to write a custom Interface that communicates with the Maingateway. We still recommend that you use IC for your custom interface as it will be updated to support newer versions of the Maingateway. 

## SUI 
Station User Interface is a user terminal and interface. It's made so it can be put on a Raspberry Pi and launch on boot. SUI updates the database using the API (see maingateway bellow). It provides the user with a interface so they can enter their personal code, scan the item and it will add the item to a database. There are 2 versions of SUI: NodeJS and Python. The NodeJS version still uses Python to read the NFC tags but the GUI uses Electron. 

## SAGI
In the future there will be a system called SAGI (Scan And Go Interface) for phones. SAGI will allow you to scan the tag, enter your code and it will be added to the database. 

## NFCDBI 
Near Field Communication DataBase Inventory is a principle for fast and easy inventory managment. NFCDBI has been redesign to provide a better interface for NFCIS (NFCDBI has only been used in a small number of projects). 

## DAUI
Desktop Admin User Interface is a extention on the Maingateway that allowes staff to connect the maingateway faster and provides a better system. 

## NFCIS Vault 
NFCIS Vault is the first prototype to make sure all the code works with the hardware. Vault uses python to allow SUI to scan and access more low level stuff. 

## Maingateway
The Maingateway is the central unit that all SUI/SAGI communitcate with. The Maingateway is a CRUD API powered by NodeJS. The Maingateway also provides a admin interface so staff can check who has what item (and when they scanned it). The API connect to the database and let's all SUI's update data. 

## Extentions
We allow for both hardware and software extentions. The SUI counts as a extention, this means that you can remove it without evrything breaking. So if you don't like the SUI you can edit it or replace it with a custom GUI. Note: SUI counts as a Base extentions meaning that it's preinstalled. We currently only have one offical extention that is both hardware and software called Card Scan (the name says what is does). This adds a new NFC read (optional, you can choose to use but there is a higher failure rate) and removes the need for a personal code. So you can give all users a FNC card/tag and they can scan it and then scan the item. This also removes the need for a touch screen (tho it's still recomended to have one). 
