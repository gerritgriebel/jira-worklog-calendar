jira-worklog-calendar
=====================

Bash CGI script which issues an ical calendar of your current Jira worklogs

The idea is to allow for a personal daily retrospective in your calendar (Google, iCalendar, Outlook, etc.). Each calendar entry has an URL to edit Jira worklog directly. For each day with worklogs there is a full day event with the total time tracked on that day.

The script contains just a single SQL which returns an ical event for each Jira worklog and in addition a full day event with the sum of all worklogs of a day.

Grab it and modify to your liking and subscribe to your new calendar.

Prerequisites
=============
- Jira on Unix and Postgres
- Access to cgi-bin direcory
- Credentials for Postgres Jira user

Installation
============

- copy the script,
- paste it into your cgi-bin directory, 
- make it executeable and 
- adjust variables inside script. Then
- run it on command line to test and 
- request it in browser. Finally
- add URL to your calendar program and
- enjoy.
