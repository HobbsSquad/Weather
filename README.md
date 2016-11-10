# Weather
<i>Raspberry Pi 3, Particle Photon, DHT, OpenHAB providing multi-device access to all things weather</i>

<h3>Overview</h3>
Ultimate goal is to have a system of sensors gathering localized envionmental data, as well as the harvesting of regional weather data (current and forecast) all being collected and recorded by a central server which then publishes the information in a pretty, easy to consume format for easy multi-platform device compatibility.
<hr>
<h3>Hardware</h3>
<B>Role:</b> Central Server<br>
<B>Hardare:</b> Raspberry Pi 3<br>
<B>Function:</b><br>
Collects input from multiple sensor nodes (see below). Utilizes internet connection to harvest current conditions and forecast data from Open Weather Map.  Records data collected from local sensor nodes and Open Weather Map data into a central database (MySQL running on the Pi). Use OpenHAB to serve up user-friendly access to environment data so that any internet-capable device can easily access the information collected by the server.<br>

<B>Role:</b>  Sensor Node<br>
<B>Hardware:</b> Photon, DHT temperature/humidity sensor, enclosure<br>
<B>Function:</b><br>
Collects temperature and humidity information from a given position in, or near, the house.  Wirelessly transmits the data to the Particle cloud. OpenHAB will use Particles REST API to harvest data and perist periodic readings in a MySQL database on the Pi.  Exterior node(s) may also measure and transmit barmetric pressure, wind speed/direction, or other conditions. Nodes will be strategically placed in and around the house and need to be discrete and out of harm's way.

<hr>
<h3>Software</h3>
<h4><b>Central Server</b></h4>
<h5>Sensor Node Communication:</h5>
Python IDE will be used write the code to control communications with the sensor nodes.<br>

<h5>Data Recording/Retrieval</h5>
MySQL RDBMS will be used to store system parameters, information about the sensor nodes (increases flexibilty to add/subtract/move nodes without changing code), as well as historical environmental/weather data.<br>

<h5>Web App</h5>
Apache will be used to serve up web pages.<br>
HTML5 and PHP will be utilized to generate static and dynamic content, including retrieval of data from MySQL<br>

<h5>NOAA Data Harvesting</h5>
Undecided.  Need more research. Possibly Python, maybe PHP? Goal is to periodically pull select data from NOAA and store in MySQL for publishing and analysis.<br>

<h4><b>Sensor Nodes</h4></b>
Arudino IDE will be used to code retievel of sensor values and transmission via RF<br>

<h4><b>Wireless Relay</h4></b>
Arudino IDE will be used to code receipving and retransmission of data via RF<br>

<hr>
<h3>Future Enhancements/Extensions</h3><br>
<list>
<li>Move DB into the cloud (AWS)</li>
<li>Move web app into the cloud</li>
<li>Add analytics, charts & graphs to evaluate environmental changes over time</li>
<li>Tie local senser nodes into HVAC system control to eliminate hot spots and cold spots and increase energy efficiency</li>
<li>Use Alexa/Echo to deliver "house status report", and serve other envrionmental data via voice command</li>
</list>
