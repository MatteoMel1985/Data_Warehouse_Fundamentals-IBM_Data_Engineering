![Skills_Network](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-PY0221EN-Coursera/images/image.png)  

<h1 align="center">Exercise 5 - Create a dashboard using Cognos Analytics</h1>

Follow these steps to upload the [DataForCognos_date.csv](/DataForCognos_date.csv) data file to Cognos Analytics:

1. Sign in to the Cognos Analytics platform with your IBMid by navigating to [myibm.ibm.com/dashboard/](myibm.ibm.com/dashboard/). Scroll down and click Launch.

![Screenshot 1](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202508/zf2wihxum8htvodyfbdv.png)  

2. In the IBM Cognos Analytics menu, click Upload data.

![Screenshot 2](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202513/e6yhref7gxacbkls7qjn.png)  

3. Once completed, the status bar will show the successful completion before closing.

![Screenshot 3](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202508/pim06ijkuufs3ojlrzrf.png)  

4. From the menu, click Recent, then select the uploaded data file DataForCognos_date.csv.

![Screenshot 4](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202509/fiz9z33io2fcqpmgf6cj.png)  

5. The template window will be displayed. Choose the four-panel template with the 2x2 configuration and click `Create`.

![Screenshot 5](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202511/ezigjqx6z7kqrl2biqj1.png)  

## ***Create a pie chart in the dashboard***  

Create a pie chart that shows the waste collected by truck type.

1. In the Navigation panel, select `Sources`. From the data source panel, press the `CTRL` key and select the attributes `Wastecollected` and `TruckType`, and drag them to the centre of Panel 1, releasing them once you see the drop zone square turn blue.

![Screenshot 6](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202512/wlz76ed4jmgmw9qiy1wr.png)  

2. Click the `Change visualization` button in the on-demand toolbar, which will  say Column.

![Screenshot 7](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202513/unbsuh4mcvoqlknztyi3.png)  

3. Expand the All visualizations panel if needed, and select `Pie`.

![Screenshot 8](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202510/siwzi4hyfq7o7bienpsi.png)  

4. Your Panel 1 visualisation should appear similar to the one below. The following are additional aesthetic changes in the image:

  * Select the title of the visualisation and change it to `Waste Collected by Truck Type`.  
  * Highlight the title text and use the on-demand toolbar to change the properties of the title:  
    * Click the colour picker icon, and change the colour to Red
    * Click the font size drop-down menu and choose 18
  * Right-click the `TuckType` legend title, select Customize Label and change the label to `Truck Type`.
  * Open the Fields panel, select Format data. Then, click the vertical ellipsis to the right of `Wastecollected` and change the data format to Number with 2 decimal places.
  * Click the `Properties` button in the top right corner to open the `Properties` panel and click the `General` tab. Expand `Appearance`, click `Border color` to open the colour options for borders, and select a black border.

![Screenshot 9](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202511/tfwrh8qlqqftpkwdotkz.png)  

## ***Create a bar chart in the dashboard***  

Create a bar chart that shows the waste collected station wise.  

1. From the `Navigation` panel, select `Sources` to ensure the data source panel is open in the left pane. From the data source panel, press the `CTRL` key and select `Wastecollected`, and `Stationid`, and drag them to the centre of Panel 2, releasing them once you see the drop zone square turn blue.

![Screenshot 10](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202509/dzluzefjdhvb4j2tirlx.png)  

2. Click the `Change visualization` button in the on-demand toolbar, which should say `Table`.

![Screenshot 11](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202510/rsutklbp6qab9pgrp0ck.png)  

3. From `Recommended visualizations` or `All visualizations`, select `Bar`.

![Screenshot 12](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202511/lu1toleuptlvb65yd411.png)  

4. Your Panel 2 visualisation should appear similar to the one below. The following are additional aesthetic changes in the image:

* Select the title of the visualisation and change it to Waste Collected by `Station ID`.
* Highlight the title text and use the on-demand toolbar to change the properties of the title:
  * Click the colour picker icon, and change the colour to red.
  * Click the font size drop-down menu and choose 18.
* Right-click the `Stationid label`, select `Customize Label` and change the label to `Station ID`.
* Right-click the `Wastecollected (Sum)` label, select `Customize Label` and change the label to `Waste Collected`.
* Click the `Properties` button in the top right corner to open the `Properties` panel and click the `General` tab. Expand Appearance, click `Border` colour to open the colour options for borders, and select a black border.  

![Screenshot 13](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202508/lbxfjxtvapxucqi1wewe.png)  

## ***Create a line chart in the dashboard***  

Create a line chart showing waste collected by month.  

1. From the `Navigation` panel, right-click the `DataForCognos_date.csv` data source and select `Calculation`.

![Screenshot 14](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202509/qjn6oiwybieroplxbwa8.png)  

2. Change the calculation name to `Month`. From the `Components` panel, click on the Functions icon, then select `Common Functions` and `D-G`. Drag `Extract` to the Expression field, and type: `month from Date_` within the parentheses. Click on the `OK` button.

![Screenshot 15](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202511/j9yltlv24wutlpoipvyr.png)  

3. From the `Navigation` panel, select `Sources` to ensure the data source panel is open in the left pane. From the data source panel, press the `CTRL` key and select `Wastecollected`, and `Month`, and drag them to the centre of Panel 3, releasing them once you see the drop zone square turn blue.

![Screenshot 16](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202512/stdmi7rtxlugcjrvjjzz.png)  

4. Your Panel 3 visualisation should appear similar to the one below. The following are additional aesthetic changes in the image:

* Select the title of the visualisation and change it to `Waste Collected by Month`.
*  Highlight the title text and use the on-demand toolbar to change the properties of the title:
  *  Click the colour picker icon, and change the colour to red.
  *  Click the font size drop-down menu and choose 18.
* Right-click the `Wastecollected (Sum)` label, select `Customize Label` and change the label to `Waste Collected`.
* Click the `Propertie`s button in the top right corner to open the Properties panel and click the `General` tab. Expand `Appearance`, click `Border color` to open the colour options for borders, and select a black border.

![Screenshot 17](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202514/waubsxnbaknz9efu4l8s.png)  

## ***Create a pie chart in the dashboard***  

Create a pie chart that shows the waste collected by the city.  

1. From the `Navigation` panel, select `Sources` to ensure the data source panel is open in the left pane. From the data source panel, press the `CTRL` key and select `Wastecollected` and `City`, and drag them to the centre of Panel 4, releasing them once you see the drop zone square turn blue.

![Screenshot 18](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202509/siriittrginy6cn6fy4x.png)  

2. Click the `Change visualization` button in the on-demand toolbar, which will currently say `Bar`.

![Screenshot 19](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202511/emawburji728q9fmffbq.png)  

3. Then expand `All visualizations`, if needed, and select `Pie`.

![Screenshot 20](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202514/al1rysl31kmn28cc5f82.png)  

4. Your Panel 4 visualisation should appear similar to the one below. The following are additional aesthetic changes in the image:

* Select the title of the visualisation and change it to `Waste Collected by City`.
* Highlight the title text and use the on-demand toolbar to change the properties of the title:
  * Click the colour picker icon, and change the colour to Red.
  * Click the font size drop-down menu and choose 18.
* Open the `Fields` panel, select `Format` data. Then, click the vertical ellipsis to the right of `Wastecollected` and change the data format to `Number` with 2 decimal places.
* Click the `Properties` button in the top right corner to open the `Properties` panel and click the `General` tab. Expand `Appearance`, click `Border color` to open the colour options for borders, and select a black border.

![Screenshot 21](https://res.cloudinary.com/dmrfsdtq2/image/upload/v1784202515/h7svf6clwnuxwzdbwuyz.png)  
