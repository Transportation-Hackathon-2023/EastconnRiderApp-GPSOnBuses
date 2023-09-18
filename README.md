# EastCONN Rider App
_Challenge #2: GPS on Buses_

## The Concept
The folks in charge of EastCONN bus dispatch told me they field a lot of phone calls asking when the bus will arrive. EastCONN buses are equipped with GPS, but the GPS vendor, Geotab, doesn't currently offer an app for riders.

An easy solution would be to post a feed of GPS information in an open data format like GTFS Realtime. Real-time bus info would then be visible in already-established third-party apps like Google Maps. However, many of EastCONN's buses serve schoolchildren, so safety concerns proscribe this.

This calls for a standalone app. We could then gate the functionality behind a sign-in, restricting it to riders and trusted adults.

## The Process
I spent the weekend diving into Geotab's REST API, trying to create a basic rider app.

I was able to create a barebones app that displays a route and the bus's location. I could also fetch a stunning amount of status info about the bus (not shown).

![screenshot](https://github.com/clairemation/eastconnRiderApp/assets/15618237/1af3cb20-4de4-4126-934d-0ee5957fb470)

However.

I couldn't find *any* way to ask the API *which stops a bus has already completed along the route*. This is necessary info.

Why?

A bus route may not be the most direct driving path. Plus, there may be dwell time at the stops. So you need to know how many stops remain before your stop, and which ones, to be able to compute the travel time.

And you can't tell this from the bus's location alone. Since the route may twist or even loop, the closest stop isn't necessarily the next one.

Thus, I wasn't able to achieve my goal with this app.

## The Takeaways
I really have to believe I just missed something here. This seems like a really obvious use case for GPS, and I can't imagine a vendor not offering it.

It's possible that Geotab's API communicates this info by removing stops from the route when the bus completes them. I wasn't able to test this since no buses were running over the weekend.
