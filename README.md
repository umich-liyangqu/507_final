# 507_final

# Required Package:
- bs4 for BeautifulSoup and web-scarping
- requests for access the webpage
- json to write the file into json fromat
- queue for BST search through data

# Instruction
Once start the game, the commend prompt will ask user to input a year between 1950 and 2022 to let the program begin gather data during those F1 season.
If player enter anything other then year between, the program will be defaulted to grab every season driver data from 1950 to 2022. Once data is grab, this will reflect in the yearly_data.json for reference. 

If the desire data is finished gathered, user can input two drivers name and the program will return how are they connected in terms of teammates and teams they have been together with. The program will count how many teams the connection have to go through as the "count".

For example, During the period of 2000~2020, the connection between two racing drivers Michael Schumacher and David Coulthard can be express in the following format:
['Michael Schumacher', 'Ferrari', 'Kimi RÃ¤ikkÃ¶nen', 'McLaren Mercedes', 'David Coulthard']
This connection will be 2, due to the two team connection it has to go through.

After a round, user can choose whether or not to try again. If user input anything but yes, the program will end. Otherwise, player can keep trying different driver connection.

# Data sturcture
Inside the Final_Project_Liyang_utl.retrive_F1com_data() function, it will scarping through each year's driver and the corrlated team information. 

The program will check if the driver's name has been collected first in a driver dictionary. If not, the program will create a new driver vertex class and putting the vertex into the dictionary using the driver name string as the key for referencing. Then the program will check if the team is existed in a team dictionary, if it does, the driver vertex will be added to the team vertex.connected_to list, and the team vertex class to the driver vertex.connected_to list. The final process will created as the following:

Vertex Driver_A: name = string driver_A connected_to = [Vertex Team A, Vertex Team B]

Vertex Team_B: name = string team_B connected_to = [Vertex Driver A, Vertex Driver B]
