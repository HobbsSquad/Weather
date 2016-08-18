# Weather
<i>Raspberry Pi, Arduinos, web-app providing multi-device access to all things weather</i>

<h3>Overview</h3>
Ultimate goal is to have a system of sensors gathering localized envionmental data, as well as the harvesting of regional weather data (current and forecast) all being collected and recorded by a central server which the publishes the information in a pretty, easy to consume format via HTTP for easy multi-platform device compatibility.

<hr>

<h3>Hardware</h3>
Final hardware choices, topology and construction is still in flux (as of 8/18/2016).  Here's the general idea:<br><br>
<B>Role:</b> Central Server<br>
<B>Hardare:</b> Raspberry Pi<br>
<B>Function:</b><br>
Collects input from multiple sensor nodes (see below). Utilizes internet connection to harvest current conditions and forecast data from NOAA.  Records data collected from local sensor nodes and possibly NOAA data into a central database (most likely MySQL running on the Pi). Use Apache and a web app to serve up user-friendly web pages so that any HTTP-capable device connected to the home network can easily access the information collected by the server.<br><br>


