# Chatbot-TPA


# Overview
This chatbot is created for the TPA coverage including both Business Partners in the ecosystem and Architects in the build movement. 

# How to upload the chatbot
To upload the chatbot into watson assistant all you have to do is download the JSON file and go to the watson assistant on the cloud. Create a new skill within the assistant and from there you can upload the JSON file into the chatbot and the chatbot skill will show up and you can work from there.

# Intents
The intents already in the chatbot are intents for the different positions and their managers. Add any other intents that you might come up along the way! 

# Entities
Currently, the entities that are used the most are partners and specialties. If you want to have a working version of the chatbot before the database is running, the best way would be to use an upgraded version of watson assistant and watson discovery in order to create a search skill. Another way to use the entities would be adding all the the IBM architects and sellers in as entities with the companies their values so that you can create an if statement/for loop to search that matches the partner to the IBM architect. However, once the cloudant database is formed the entities might not be as important because once you integrate cloudant as the data source the chatbot can use search skills to search the cloudant database. 

# Dialog
The chatbot is split into dialog nodes first arranged by position: 
TPS (including managers), TPA (including managers), BSPS, person in charge of GSI, CSM, SL, Digital reps, and Watson Sellers

For TPS, TPA, BSPS, and GSI there are up to 8 specialties in each position: AI Apps (or AI), Security (SEC), Data analytics (Data), Cloud platform (Cloud or CP), C&DP, Storage, Power and Z

Currently the dialog of the chatbot will check for the name of the partner and ask if the user wants to input a specific speacialty. Then it will jump to a child node of the dialog that corresponds with the specific specialty. Once it's in the child node, it searches for the name of the partner among the list and will return the name of the TPA/TPS/BSPS/GSI that corresponds to the partner. If the partner's name cant be found then the chatbot will return "The partner currently doesn't have a ____".

# Integration with Cloudant and watson discovery
This is a great walkthrpugh i found in the github repository on how to intergrate the chatbot with watson discovery and cloudant which is what jenny wants to be able to do once the cloudant database is finished:
https://github.com/IBM/watson-online-store#5-configure-watson-discovery

# What's left 
Look through the positions to see which need to be finished. There are new excel sheets that were sent last week which includes GSIs and TPAs (2021 GSI TPA Coverage) that are in charge of the build motion so that will need to be put into the chatbot. Additionally, when looking at the Build Partners Account List excel sheet make sure to look at the BUILD-TPS TPa account excel sheet in conjunction to check for the first line manager and any missing TPA positions. 

Link the watson assistant to watson discovery in order to use the search skill. Right now, you can upload the excel documents into watson discovery and link those to the chatbot responses to search through the excel documents. In future iterations use the paragraph above to integrate cloudant and watson discovery with the chatbot. That way it will be more straightforward in the dialog once youre able to integrate the two databases.
