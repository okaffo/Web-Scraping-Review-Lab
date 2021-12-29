# Web-Scraping-Review-Lab
Objectives
After completing this lab you will be able to:

Download a webpage using requests module
Scrape all links from a web page
Scrape all image urls from a web page
Scrape data from html tables
Scrape www.ibm.com
Import the required modules and functions

from bs4 import BeautifulSoup # this module helps in web scrapping.
import requests  # this module helps us to download a web page
Download the contents of the web page

url = "http://www.ibm.com"
# get the contents of the webpage in text format and store in a variable called data
data  = requests.get(url).text 
Create a soup object using the class BeautifulSoup

soup = BeautifulSoup(data,"html5lib")  # create a soup object using the variable 'data'
Scrape all links

for link in soup.find_all('a'):  # in html anchor/link is represented by the tag <a>
    print(link.get('href'))
#main-content
http://www.ibm.com
https://www.ibm.com/thought-leadership/best-of/2021/?lnk=ushpv18l1
https://www.ibm.com/thought-leadership/institute-business-value/report/2021-cto?lnk=ushpv18f1
https://www.ibm.com/products/supply-chain-intelligence-suite?lnk=ushpv18f2
https://www.ibm.com/it-infrastructure/z/zos?lnk=ushpv18f3
https://www.ibm.com/cloud/hybrid/value-calculator/?lnk=ushpv18f4
https://www.ibm.com/products/offers-and-discounts?link=ushpv18t5&lnk2=trial_mktpl_MPDISC
https://www.ibm.com/cloud/openshift/get-started?lnk=ushpv18t1&lnk2=trial_RedHatOpenShift&psrc=none&pexp=def
https://www.ibm.com/cloud/cloud-pak-for-integration?lnk=ushpv18t2&lnk2=trial_CloudPakInt&psrc=none&pexp=def
https://www.ibm.com/products/planning-analytics?lnk=ushpv18t3&lnk2=trial_PlanningAnalytics&psrc=none&pexp=def
https://www.ibm.com/cloud/free?lnk=ushpv18t4&lnk2=trial_Cloud&psrc=none&pexp=def
https://www.ibm.com/search?lnk=ushpv18srch&locale=en-us&q=
https://www.ibm.com/products?lnk=ushpv18p1&lnk2=trial_mktpl&psrc=none&pexp=def
https://www.ibm.com/cloud/hybrid?lnk=ushpv18pt14
https://www.ibm.com/watson?lnk=ushpv18pt17
https://www.ibm.com/it-infrastructure?lnk=ushpv18pt19
https://www.ibm.com/us-en/products/categories?technologyTopics%5B0%5D%5B0%5D=cat.topic:Blockchain&isIBMOffering%5B0%5D=true&lnk=ushpv18pt4
https://www.ibm.com/us-en/products/category/technology/security?lnk=ushpv18pt9
https://www.ibm.com/us-en/products/category/technology/analytics?lnk=ushpv18pt1
https://www.ibm.com/cloud/automation?lnk=ushpv18ct21
https://www.ibm.com/quantum-computing?lnk=ushpv18pt16
https://www.ibm.com/mysupport/s/?language=en_US&lnk=ushpv18ct11
https://www.ibm.com/training/?lnk=ushpv18ct15
https://developer.ibm.com/?lnk=ushpv18ct9
https://www.ibm.com/garage?lnk=ushpv18pt18
https://www.ibm.com/docs/en?lnk=ushpv18ct14
https://www.redbooks.ibm.com/?lnk=ushpv18ct10
https://www-03.ibm.com/employment/technicaltalent/developer/?lnk=ushpv18ct2
https://www.ibm.com/
Scrape all images

for link in soup.find_all('img'):# in html image is represented by the tag <img>
    print(link.get('src'))
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTA1NSIgaGVpZ2h0PSI1MjcuNSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
 https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/48/55/20211220-best-of-2021-mobile-720x360.jpg
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDQwIiBoZWlnaHQ9IjMyMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/e7/ed/20211220-CTO-animated-spiral-444x320.gif
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDQwIiBoZWlnaHQ9IjMyMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/05/18/20211220-ls-supply-chain-intelligence-suite-26098-444x320.jpg
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDQwIiBoZWlnaHQ9IjMyMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/b6/5e/2021104-Z-OS-2-5-26126-444x320.jpg
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDQwIiBoZWlnaHQ9IjMyMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/30/92/20210712-f-hybrid-cloud-value-calculator.jpg
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDQwIiBoZWlnaHQ9IjI2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/98/90/OpenShift-Cloud-23811-700x420.png
data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDQwIiBoZWlnaHQ9IjI2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/25/ff/cloud-pak-for-integration-444x254.png
data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDQwIiBoZWlnaHQ9IjI2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/22/af/Planning-Analytics-22201-700x420.png
data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7
data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDQwIiBoZWlnaHQ9IjI2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB2ZXJzaW9uPSIxLjEiLz4=
https://1.dam.s81c.com/public/content/dam/worldwide-content/homepage/ul/g/54/79/IBM-Cloud-23059-700x420.png
data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7
Scrape data from html tables
#The below url contains a html table with data about colors and color codes.
url = "https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DA0321EN-SkillsNetwork/labs/datasets/HTMLColorCodes.html"
Before proceeding to scrape a web site, you need to examine the contents, and the way data is organized on the website. Open the above url in your browser and check how many rows and columns are there in the color table.

# get the contents of the webpage in text format and store in a variable called data
data  = requests.get(url).text
soup = BeautifulSoup(data,"html5lib")
#find a html table in the web page
table = soup.find('table') # in html table is represented by the tag <table>
#Get all rows from the table
for row in table.find_all('tr'): # in html table row is represented by the tag <tr>
    # Get all columns in each row.
    cols = row.find_all('td') # in html a column is represented by the tag <td>
    color_name = cols[2].getText() # store the value in column 3 as color_name
    color_code = cols[3].getText() # store the value in column 4 as color_code
    print("{}--->{}".format(color_name,color_code))
Color Name--->Hex Code#RRGGBB
lightsalmon--->#FFA07A
salmon--->#FA8072
darksalmon--->#E9967A
lightcoral--->#F08080
coral--->#FF7F50
tomato--->#FF6347
orangered--->#FF4500
gold--->#FFD700
orange--->#FFA500
darkorange--->#FF8C00
lightyellow--->#FFFFE0
lemonchiffon--->#FFFACD
papayawhip--->#FFEFD5
moccasin--->#FFE4B5
peachpuff--->#FFDAB9
palegoldenrod--->#EEE8AA
khaki--->#F0E68C
darkkhaki--->#BDB76B
yellow--->#FFFF00
lawngreen--->#7CFC00
chartreuse--->#7FFF00
limegreen--->#32CD32
lime--->#00FF00
forestgreen--->#228B22
green--->#008000
powderblue--->#B0E0E6
lightblue--->#ADD8E6
lightskyblue--->#87CEFA
skyblue--->#87CEEB
deepskyblue--->#00BFFF
lightsteelblue--->#B0C4DE
dodgerblue--->#1E90FF
Authors
Ramesh Sannareddy

Other Contributors
Rav Ahuja

Change Log
Date (YYYY-MM-DD)	Version	Changed By	Change Description
2020-10-17	0.1	Ramesh Sannareddy	Created initial version of the lab
Copyright © 2020 IBM Corporation. This notebook and its source code are released under the terms of the MIT License.
