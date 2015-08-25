# Boomerang.io Python API client

Example

import calendar
import datetime
from boomerang.client import BoomerangClient

bc = BoomerangClient(projectid, apikey)

future = datetime.datetime.utcnow() + datetime.timedelta(minutes=5)
date = calendar.timegm(future.timetuple())
boomerang_stuff = { "url": "http://localhost:5000", "msg": "test", "run_at": date }

print bc.delete_boomerang('2ffd53e9d21199b5').text
print bc.create_boomerang(boomerang_stuff).text
print bc.get_all_boomerangs().text