# smartair-mqtt
utility to for polling smartairs "hub" and publishing it to mqtt in a format home assistant understands

# Compability
Tested against a VTR-100 with the Internet access module (IAM). Might work against other models, or it might just break them.

# Status
This software is very much "use at your own risk" and is to be considered pre-alpha quality. I've added the registers I'm currently most interrested in. There's also no retry if updating a registry fails, which causes the entity in HA to show the invalid value until it can successfully poll the IAM module again.

The IAM module has issues doing quick successive queries and updates, which can cause problems if you're accessing the web ui of the IAM module at the same time as this application is running.

# Prerequisits
Node 18 with npm. Might work on other versions, but who knows

# How to
`npm install && node smartair.js`

There is almost no error handling, so I'm currently running it with:
`while true; node smartair.js; sleep 10; end`
