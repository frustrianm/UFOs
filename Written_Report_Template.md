# UFO Sighting with JavaScript - FRM's Tec Data Bootcamp Challenge #11

## Overview of the Analysis
### Purpose
For this challenge we had the task of helping Dana's dynamic webpage not only to filter data based on an input date, but to filter it with 4 new data criterias to tighten the search of specific UFO sightings base on:
- Date (already existing filter before the challenge)
- City (new filter)
- State (new filter)
- County (new filter)
- Shape (new filter)

These new filters broaden Dana's webpage query power and make it easier for users to find rather specific data based on 5 filters rather than been guided only by the date.

## Results
### Description of the search
- Opening Page
Dana's webpage users will land to this webpage powered by Javascript, HTML and CSS.
![Landing Page](https://user-images.githubusercontent.com/96660344/169660232-fe57ba75-f964-4dee-9602-f317bfb72ecd.png)

- Filters
The filters are displayed in the webpage based on the following HTML code:
```
                <ul class="list-group bg-dark">
                    <li class="list-group-item bg-dark">
                        <label for="date">Enter Date</label>
                        <input type="text" placeholder="1/10/2010" id="datetime" />
                    </li>
                    <li class="list-group-item bg-dark">
                        <label for="city">Enter City</label>
                        <input type="text" placeholder="benton" id="city" />
                    </li>
                    <li class="list-group-item bg-dark">
                        <label for="state">Enter State</label>
                        <input type="text" placeholder="ca" id="state" />
                    </li>
                    <li class="list-group-item bg-dark">
                        <label for="country">Enter Country</label>
                        <input type="text" placeholder="us" id="country" />
                    </li>
                    <li class="list-group-item bg-dark">
                        <label for="shape">Enter Shape</label>
                        <input type="text" placeholder="circle" id="shape" />
                    </li>
                </ul>
```
In this dynamic area, users can modify the parameters desired to find data they're looking for.

![Filter](https://user-images.githubusercontent.com/96660344/169660342-bd63e919-514d-4932-b964-2193e1a75c50.png)

- Table
The table with new input data is powered by the following code:
```
// 7. Use this function to filter the table when data is entered.
function filterTable() {

  // 8. Set the filtered data to the tableData.
  let filteredData = tableData;

  // 9. Loop through all of the filters and keep any data that
  // matches the filter values
  Object.keys(filters).forEach((filter) => {
    filteredData = filteredData.filter(row => row[filter] === filters[filter]);
    }
  );
  
  // 10. Finally, rebuild the table using the filtered data
  buildTable(filteredData);
}
```
As seen in the following picture, we are looking for the "light" sighting shape in "Texas (tx)" state, and the table is retrieve such data for us and displays it.
![Table](https://user-images.githubusercontent.com/96660344/169660463-6180af38-0f68-4bfb-89a0-dccf51cb345e.png)

## Summary
### Main drawback
At first glance, this HTML file helps us to find useful info for anyone interested in UFO sightings but since the data is static and loaded from a JavaScript file, unless we manually update the data it won't have new entries and the webpage can become irrelevant in short time.

### Recommendation for further improvement 1
To enter the data we want to get, we have to know what data we can enter, and unless we have the JavaScript data file we'll know all the possible data we could look for. A dropwdown list with all the possible options in each filter might make users take more advantage of the webpage, instead of writing the input that may not be correctly written and data will not be delivered (writing texas instead of "tx") or that may not even exist and the user may not know so.

### Recommendation for further improvement 2
Most webpages and apps where we can look for data still include an action button. Having the app.js to listen to the changes in the code is a great advantage, I found it a bit tricky when first wrote an input and the table did not changed until I pressed "Enter". With an casual action button it may be less confusing for users who might think the webpage filter is not working.
