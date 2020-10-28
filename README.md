# OBSTimeDDisplayPlugin
A JavaScript plugin to display current time and date (yes the double Ds in the name are on purpose, it's a thing for my programs)  


Displays current time and date in a 12 hour format with month spelled out and date with st/nd/rd/th format as per example:  

"5:30PM Monday September 14th 2020". Font is black in color by default and font is Time New Roman on Windows.  

To use: Download and unzip HTML file. Then add to OBS as a Browser source, make sure to check "local file", and point to this HTML file locally saved on your hard drive.
Height and width will vary depending on font used (see below on how to customize), but I have seen that width in the 200 - 250 range and height in the 20-50 range work pretty well for a 12 point font.  
  
______________________________________________  
V2.0 update - created sections:  
timeStdDisp (shows standard time),  
ampmDisp (AM/PM),  
timeMilDisp (shows time in "military" format, default hidden),  
dayOfWeekDisp (full day name display),  
monthNameDisp (full month name display),  
dayOfMonthDisp (one or two digit day),  
dayModDisp (st/nd/rd/th),  
yearDisp (four digit year display)  
  
V2.1 bugfixes:  
Issue with Saturday showing as ERR  
Fixed issue with 12:00 - 12:59 showing as AM instead of PM in 12 hour mode  
______________________________________________  
  
With these sections implemented in v2.0 you can update each area to your liking via CSS in OBS without changing any of the script code itself, or display military time format while hiding standard time format. The following are some of the ways you can update the display in Custom CSS field in OBS.  

Update font information for all items(this sets to Arial, 12 pixels):  
body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden; font-family: Arial; font-size: 12px;}  

Update color for all items globally (updated the Arial 12point font to white):  
body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden; font-family: Arial; font-size: 12px; color:#FFFFFF;}  

Text fonts and colors can be referenced multiple ways in CSS. Please refer online to find valid color and font choices.  
I recommend W3Schools articles:  
https://www.w3schools.com/css/css_font.asp  
https://www.w3schools.com/cssref/css_websafe_fonts.asp  
https://www.w3schools.com/css/css_colors.asp  
https://www.w3schools.com/colors/colors_hex.asp  


To change color of a section after the 'body' tag add a line in Custom CSS to be for the section (in #sectionname notation) that you would like to update.  

To change color of just one section (in this example the AM/PM flag to magenta while the rest of the text is white):  
body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden; font-family: Arial; font-size: 12px; color:#FFFFFF;}  
#ampmDisp { color:#FF00FF;}  

To remove an area (in this example hiding both the AM/PM flag and the dayModDisp):  
body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden; font-family: Arial; font-size: 12px; color:#FFFFFF;}  
#ampmDisp { display:none; }  
#dayModDisp { display:none;}  

To change to military time, PLEASE REMEMBER - you will have to hide standard time display and AM/PM display while also showing Military Time display:  
body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden; font-family: Arial; font-size: 12px; color:#FFFFFF;}  
#timeStdDisp { display:none;}  
#ampmDisp { display:none; }  
#timeMilDisp { display:inline;}  

Using a combination of these items you can customize the time display to your liking. For example I wanted the time to be a different color and font 
than the rest of the day display and used the following CSS:  
body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden; font-family: "Trebuchet MS"; font-size: 12px; color:#FFFACD;}  
#timeStdDisp { color:#FFD700; font-family: Arial;}  
#ampmDisp { color:#FFD700; font-family: Arial;}  





