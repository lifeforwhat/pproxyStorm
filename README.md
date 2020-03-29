# pproxyStorm
Create as many proxies as you want, as many NICs you have.

# TEST

pproxy -l http://192.168.130.1:20000/@123.123.123.123

Serving on 192.168.130.1:20000 by http 

pproxy -l http://192.168.130.1:20001/@192.168.100.8

Serving on 192.168.130.1:20001 by http 

pproxy -l http://192.168.130.1:20002/@192.168.1.25

Serving on 192.168.130.1:20002 by http 

pproxy -l http://192.168.130.1:20003/@192.168.0.62

Serving on 192.168.130.1:20003 by http 

pproxy -l http://192.168.130.1:20004/@123.123.123.123

Serving on 192.168.130.1:20004 by http 

pproxy -l http://192.168.130.1:20005/@123.123.123.123

Serving on 192.168.130.1:20005 by http 

pproxy -l http://192.168.130.1:20006/@123.123.123.123

Serving on 192.168.130.1:20006 by http 

pproxy -l http://192.168.130.1:20007/@123.123.123.123

Serving on 192.168.130.1:20007 by http 


# RESULT
print(requests.get('http://api.ipify.org?format=json' , proxies={'http' : 'http://192.168.130.1:20000'}).text)

{"ip":"123.123.123.123"}

print(requests.get('http://api.ipify.org?format=json' , proxies={'http' : 'http://192.168.130.1:20001'}).text)

{"ip":"123.123.123.123"}

print(requests.get('http://api.ipify.org?format=json' , proxies={'http' : 'http://192.168.130.1:20002'}).text)

{"ip":"123.123.123.123"}

print(requests.get('http://api.ipify.org?format=json' , proxies={'http' : 'http://192.168.130.1:20003'}).text)

{"ip":"123.123.123.123"}

print(requests.get('http://api.ipify.org?format=json' , proxies={'http' : 'http://192.168.130.1:20004'}).text)

{"ip":"123.123.123.123"}

print(requests.get('http://api.ipify.org?format=json' , proxies={'http' : 'http://192.168.130.1:20005'}).text)

{"ip":"123.123.123.123"}

print(requests.get('http://api.ipify.org?format=json' , proxies={'http' : 'http://192.168.130.1:20006'}).text)

{"ip":"123.123.123.123"}

print(requests.get('http://api.ipify.org?format=json' , proxies={'http' : 'http://192.168.130.1:20007'}).text)

{"ip":"123.123.123.123"}

