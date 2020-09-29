# pysolar_civil-nautical-astronomical

########################## Sunrise Sunset ##################################################

SUN_ZENITH_SUNRISE_SUNSET = 0
SUN_ZENITH_CIVIL_TWILIGHT = 1
SUN_ZENITH_NAUTICAL_TWILIGHT = 2
SUN_ZENITH_ASTRONOMICAL_TWILIGHT = 3

fecha = dt.now()
tz = pytz.timezone('UTC')
fecha = fecha.replace(tzinfo=tz)
sr, ss, tr = get_sunrise_sunset_transit(latitud, longitud, fecha, SUN_ZENITH_ASTRONOMICAL_TWILIGHT)
# Horario de verano
sr = sr + timedelta(hours=1)
ss = ss + timedelta(hours=1)
tr = tr + timedelta(hours=1)
print('sunrise: ', sr.strftime("%Y-%m-%d %H:%M:%S"))
print('sunset:', ss.strftime("%Y-%m-%d %H:%M:%S"))
print('transit:', tr.strftime("%Y-%m-%d %H:%M:%S"))
