![#Booker](http://i.imgur.com/hGZAo5n.png)

*All your room are belong to us!*
## Intro
__Booker__ is a set of python 3 scripts that automatically book group study rooms at the ANU library.

## Warning
It is in a very early development stage, core functions are still being implemented. No features are available as of yet.
All of the code is being written by two first-year engineering students, so its quality it pretty terrible (sorry).

## Planned features
+ Auto-book rooms for every timetable break
+ Multiple ANU accounts (more concurrent bookings)
+ Configurable timetable, room preferences, libraries
+ Email notifications or Google calendar integration

## Technical stuff
__Booker__ uses _requests_ python library to interact with the _anulib.anu.edu.au_ website. All the information is stored in plain-text .conf files.

Apart from the main __booker.py__ script, there are multiple utility modules:
+ __config.py__ works with (you guessed it), .conf files, storing and loading information from them.
+ __network.py__ contains functions to interact with the _anulib_ website.
+ __notify.py__ generates and sends out email notifications and works with the calendar.

The configuration files are:
+ __timetable.conf__ contains information about breaks during which the rooms need to be booked.
+ __login.conf__, which is not actually present on the repo for obvious reasons, contains a list of logins and passwords to be used for booking. (There's an __.example__ file provided).
+ __cbook.conf__ stores all the current bookings.
+ __email.conf__ will be used for all notificaton-related stuff.
+ __rooms.conf__ is a room preference file (some study rooms are much better than the others).

## Booking Restrictions
+ 2x 2hr bookings / day (4hrs / day)
+ 5x bookings / 10 days (10hrs / 10 days)
+ To completely book out a room from 8am 'til midnight is 16 hours, or 4 people's bookings
+ 8 people can saturate a room's booking for 1 week, every 2 weeks
+ To permanently book a room (weekdays) indefinitely, 16 people's logins are required.

More appropriate would be to book a room from 10am - 8pm (10 hrs / day), 2.5 people's bookings
To continue this booking for a full week would require 5 people, on a bi-weekly basis, or 10 for
complete saturation.
