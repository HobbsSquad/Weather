# Weather
<i>Raspberry Pi, Arduinos, web-app providing multi-device access to all things weather</i>

<h3>Overview</h3>
Ultimate goal is to have a system of sensors gathering localized envionmental data, as well as the harvesting of regional weather data (current and forecast) all being collected and recorded by a central server which then publishes the information in a pretty, easy to consume format via HTTP for easy multi-platform device compatibility.
<hr>
<h3>Hardware</h3>
Final hardware choices, topology and construction is still in flux (as of 8/18/2016).  Here's the general idea:<br><br>
<B>Role:</b> Central Server<br>
<B>Hardare:</b> Raspberry Pi, RF receiver<br>
<B>Function:</b><br>
Collects input from multiple sensor nodes (see below). Utilizes internet connection to harvest current conditions and forecast data from NOAA.  Records data collected from local sensor nodes and possibly NOAA data into a central database (most likely MySQL running on the Pi). Use Apache and a web app to serve up user-friendly web pages so that any HTTP-capable device connected to the home network can easily access the information collected by the server.<br>

<B>Role:</b>  Sensor Node<br>
<B>Hardware:</b> Arduino, temperature/humidity sensor, RF transmitter, enclosure<br>
<B>Funcition:</b><br>
Collects temperature and humidity information from a given position in, or near, the house.  Wirelessly transmits the data to the central server. Exterior node(s) may also measure and transmit barmetric pressure, wind speed/direction, or other conditions. Nodes will be strategically placed in and around the house and need to be discrete and out of harm's way.

<b>Role:</b>  Wireless Relay<br>
<B>Hardware:</b> Arduino, RF Receiver, RF transmitter, enclosure<br>
<b>Function:</b><br
Ensures a strong, consistent delivery of data from sensor nodes to the central server.  Will be strategically placed in the home as needed to receive signals from the sensor nodes and relay out to other relays and/or the central server.
<hr>
<h3>Software</h3>
<b>Central Server</b><br>
<b>Sensor Node Communication:</b><br>
Python IDE will be used write the code to control communications with the sensor nodes.<br>

<b>Data Recording/Retrieval<b><br>
MySQL RDBMS will be used to store system parameters, information about the sensor nodes (increases flexibilty to add/subtract/move nodes without changing code), as well as historical environmental/weather data.<br>

<b>Web App</b><br>
Apache will be used to serve up web pages.<br>
HTML5 and PHP will be utilized to generate static and dynamic content, including retrieval of data from MySQL<br>

<b>NOAA Data Harvesting</b><br>
Undecided.  Need more research. Possibly Python, maybe PHP? Goal is to periodically pull select data from NOAA and store in MySQL for publishing and analysis.<br>


