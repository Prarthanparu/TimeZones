# TimeZones
List of all Countries TimeZones in Alphabetical Order

import pytz
import datetime

country = 'Europe/London'
tz_to_display = pytz.timezone(country)
local_time = datetime.datetime.now(tz=tz_to_display)

print("The time in {} is : {}".format(tz_to_display,local_time))
print("UTC is : {}".format(datetime.datetime.utcnow()))

for x in sorted(pytz.country_names):
    print("{} : {} ".format(x,pytz.country_names[x]), end=':  ')
    if x in pytz.country_timezones:
        for zone in sorted(pytz.country_timezones[x]):
            tz_to_display = pytz.timezone(zone)
            local_time = datetime.datetime.now(tz=tz_to_display)
            print("{} : {} ".format(zone,local_time))
    else:
        print("\t\tNo time Zone available")
