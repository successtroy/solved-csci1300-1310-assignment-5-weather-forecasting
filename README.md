Download Link: https://assignmentchef.com/product/solved-csci1300-1310-assignment-5-weather-forecasting
<br>



<ol>

 <li>Apply the concept of program decomposition.</li>

 <li>Populate an array of structs from a file.</li>

 <li>Design functions that access the attributes of a struct.</li>

</ol>




In this assignment, you will process a file of weather forecasting data for Boulder and answer a few questions about the weather. There is a file on moodle called

​         <em>boulderData</em> that contains comma-delimited information about the weather forecast for each day and the next three days.




The first day in the file is January 26, 2016 and the last day in the file is September 29, 2016. The format for each line in the file is as follows:




<table width="0">

 <tbody>

  <tr>

   <td width="44">Day</td>

   <td width="66">Forecast day</td>

   <td width="48">High temp</td>

   <td width="54">Low temp</td>

   <td width="78">Humidity</td>

   <td width="66">Avg. wind</td>

   <td width="66">Avg.wind direct.</td>

   <td width="51">Max. wind</td>

   <td width="58">Max.wind direct.</td>

   <td width="66">Precip</td>

  </tr>

  <tr>

   <td width="44">1-26-2016</td>

   <td width="66">1-26-2 016</td>

   <td width="48">H:40</td>

   <td width="54">L:26</td>

   <td width="78">43</td>

   <td width="66">6</td>

   <td width="66">WNW</td>

   <td width="51">10</td>

   <td width="58">WNW</td>

   <td width="66">0.0</td>

  </tr>

 </tbody>

</table>




<strong>Day:</strong> The current day​




<strong>Forecast day:</strong> The day that the forecast is for. In this example, the day and forecast​   day are the same, which means it’s the forecast for 1-26-2016 on 1-26-2016. There are other lines in the file that show the forecast for a future day. For example, if the day were 1-26-2016 and forecast day were 1-27-2016, it would be the forecast for 1-27-2016 issued on 1-26-2016.




<strong>High temp:</strong> The forecasted high temp for the forecast day.​




<strong>Low temp:</strong> The forecasted low temp for the forecast day.​




<strong>Humidity:</strong> The forecasted humidity for the forecast day.​

<strong>Avg. wind:</strong> The forecasted average wind speed for the forecasted day.​




<strong>Avg. wind direction:</strong> The forecasted average wind direction for the forecasted day.​




<strong>Max. wind:</strong> The forecasted maximum wind speed for the forecasted day.​         <strong>Max. wind direct.:</strong> The forecasted direction for the maximum wind speed for the​  forecasted day.




<strong>Precip.:</strong> The forecasted precipitation.​




<h2>Assignment Details</h2>

For this assignment, you need to read in the data stored in the file and store it in an array of structs of maximum 10 elements. Your struct should have the following minimum set of attributes:




struct Forecast{     string day;     int highTemp;     int lowTemp;     int humidity;     int avgWind;     string avgWindDir;     int maxWind;     string maxWindDir;     double precip;

};




Store only the most current forecast for each day, this would be the lines in the file where the Day and Forecast day are the same. Discard the other lines in the file by not reading them into your array. Your array will need to store 245 days worth of data.

NOTE: If you’re planning to do the additional functions suggested below, After submitting the assignment in moodle, modify your program to store all of the data and add an additional parameter to your struct for forecast day.




<h3>Functions that need to be in your program</h3>

<strong> </strong>

void populateArray(string filename,Forecast forecastData[]);

<ul>

 <li>Populates the array reading data from file called filename.</li>

</ul>




string lastDayItRained(Forecast forecastData[]);

<ul>

 <li>Returns the date of the last day it rained.</li>

</ul>




double totalRainfall(Forecast forecastData[]);

<ul>

 <li>Returns the sum of the precipitation in the data set.</li>

</ul>







int maxWindspeed(Forecast forecastData[]);

<ul>

 <li>Returns the index in the array where the maximum wind speed is found.</li>

</ul>




int maxRainfall(Forecast forecastData[]);

<ul>

 <li>Returns the index in the array where the maximum precipitation is found.</li>

</ul>




int maxTempDifference(Forecast forecastData[]);

<ul>

 <li>Returns the index in the array where with the maximum difference between the high and low temperature.</li>

</ul>




Forecast forecastForDay(Forecast forecastData[], string day); ● Returns the forecast for a particular day in the array.

<strong> </strong>

<h3>Functionality in main()</h3>

In your <em>main()</em>​ function, declare Forecast struct array and call the populateArray function passing the filename and the struct array. Once you’re confident that the array data is correct, call the other functions to analyze the data and print the results. Your output should look like this:




Forecast statistics:

Last day it rained: &lt;date of last rain event&gt;

Total rainfall: &lt;sum of precipitation&gt;

Maximum wind speed: &lt;wind mph&gt; mph on &lt;date&gt;

Maximum rainfall: &lt;precipitation&gt; inches on &lt;date&gt;

Maximum temperature difference: &lt;high – low&gt; F on &lt;date&gt;




Further your main function should prompt the user for a date and display the forecast for that date. If the date is not found in the file, your program should print “Date not found.”




cout&lt;&lt;”Enter a date:”; getline(cin, date)

Forecast dayForecast = forecastForDay(forecastData, date);




Forecast for &lt;date&gt;:

H: &lt;high temp&gt;

L: &lt;low temp&gt;

Humidity: &lt;humidity&gt;

Avg. wind: &lt;avg wind speed&gt;

Avg. wind direction: &lt;avg wind direction&gt;

Max wind: &lt;max wind speed&gt;

Max wind direction: &lt;max wind direction&gt;

Precipitation: &lt;precip&gt;







<strong>Additional practice problems: </strong>

If you are interested in additional problems for practice, here are a few more functions you can work on. We won’t be grading them, but a little extra practice never hurt anyone.




<ol>

 <li>Determine the day of the year when the three-day forecast and the day-of forecast showed the greatest difference for high temperature. If there are ties, print all days with the greatest difference.</li>

 <li>Determine how accurate the precipitation forecast is for one, two, and three days from the current day.</li>

 <li>Find the missing data point(s). There is at least one day of data missing from the file. Write a function to find it.</li>

</ol>