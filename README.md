# Log_Script
 This is a simple shell script for analysing log details. It simply grab all the IP's of the visitors who try to access a hosted webserver on a linux machine
 
### Script for grabbing all the intruders IP.

 	#!/bin/bash
     for x in $(cat /var/log/httpd/access_log | grep -E -o "([0-9]{1,3}[\.]){3}[0-9]{1,3}" | sort -u)
     do
      echo "visitor: $x" >> /root/visitor.txt
     done

### Whole script is kept inside a for loop

		for VARIABLE in $(linux-Or-Unix-Command-Here)
		do
			command on $VARIABLE
		done

### The "cat" command help us to read, view, concatenate files. So here it is use to access the 'access_log' file from the  "var/log/httpd" directory.

### The Grep (stands for globally search for regular expression & print out) filter searches a file for a particular pattern of characters & display  all lines that contain that pattern. The pattern that is searched in the file is referred to as the regular expression.

         # Syntax:

         '''
         	grep [options] pattern [files]

         	Options Description
         	-E : Treats pattern as an extended regular expression (ERE)
         	-o : Print only the matched parts of a matching line, with each such part on a separate output line.

         '''
### Simple regular Expression to validate an IP address:
		
			([0-9]{1,3}[\.]){3}[0-9]{1,3}
		
### The sort command is used to rearrange the contents of a file line by line. This command is a filter that sorts the input text & prints the results to stdout. 
		# Syntax:

		'''
			sort [options][files]

			Options Description

			sort -u: Suppress line that repeat an earlier key
		'''
### A simple 'do done' loop is followed at the end of the script to store the generated output in a file called 'visitor.txt' in the root directory of the linux file system.
