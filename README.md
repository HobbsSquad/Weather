# Weather
<i>Raspberry Pi 3, Particle Photon, DHT, and OpenHAB providing multi-device access to all things weather</i>

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
Collects temperature and humidity information from a given position in, or near, the house.  Wirelessly transmits the data to the Particle cloud. OpenHAB will use Particle's REST API to harvest data and perist periodic readings in a MySQL database on the Pi.  Exterior node(s) may also measure and transmit barmetric pressure, wind speed/direction, or other conditions. Nodes will be strategically placed in and around the house and need to be discrete and out of harm's way.

<hr>
<h3>Software</h3>
<h4><b>Central Server</b></h4>
<h5>Data Recording/Retrieval</h5>
MySQL RDBMS will be used to store system parameters, information about the sensor nodes (increases flexibilty to add/subtract/move nodes without changing code), as well as historical environmental/weather data.<br>

<h5>Web App</h5>
OpenHAB home automation system will be used to persist historical data, as well as providing a user-friendly interface for presenting weather data.  OpenHAB has the ability to connect with the Photon's via the Particle cloud and its REST API.  It can also connect to a local MySQL database to persist the data.  OpenHAB also has built-in hooks to several weather data providers which will be utilized to gather regional weather conditions and forecast data.<br>

<h5>Open Weather Map Data Harvesting</h5>
The built-in hook from OpenHAB to Open Weather Map will be configured to display current conditions, forecast information and to harvest and record historical data<br>

<h4><b>Sensor Nodes</h4></b>
Particle Dev IDE will be used to code retievel of sensor values and transmission via WiFi<br>

<hr>
<h3>Future Enhancements/Extensions</h3><br>
<list>
<li>Add analytics, charts & graphs to evaluate environmental changes over time</li>
<li>Tie local senser nodes into HVAC system control to eliminate hot spots and cold spots and increase energy efficiency</li>
<li>Use Alexa/Echo to deliver "house status report", and serve other envrionmental data via voice command</li>
</list>
