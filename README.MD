# Logs

This repository contains a function to log anything inside a **nodeJs** script, this is how it works

**1st** include the script to yours

**2nd** write this function log("Log Message")

The script will automatically log on the console the _Log Message_ using this format _**DD/MM/YYYY | HH:MM:SS:MMM**_ and then write the same message on the _log.txt_

____________________________________________________________________________________________________________________________________________________________

# How it works

The code is splittable in 3 parts 


1. The function to obtain date and time. 
2. The function that writes the log to the _log.txt_ file
3. The function to write the log to the console


1: 
  
  <code>// time
  const fs = require("fs")
  var year = new Date().getFullYear();
  var month = new Date().getMonth();
  var day = new Date().getDate();
  var hours = new Date().getHours();
  var minutes = new Date().getMinutes();
  var seconds = new Date().getSeconds();
  var milliseconds = new Date().getMilliseconds();
  var time = day + "/" + month + "/" + year + " | " + hours + ":" + minutes + ":" + seconds + ":" + milliseconds;
</code>

2:

<code>// write to log.txt
  fs.appendFile("./log.txt", message + "\n", (err) => {
    if (err) {
      console.error(err);
      return;}});</code>

3: 

<code>// print to console
  console.log(message);</code>
