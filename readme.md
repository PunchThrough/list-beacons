# List Beacons

A simple Node.js utility to list nearby iBeacons.

# Setup

Clone this repo, then `cd` into it and run `npm install` to install its dependencies.

# Usage

Run `node index.js` to start scanning for nearby iBeacons. You'll see the UUID, major, and minor values of nearby iBeacons as they advertise:

```
$ node index.js
0: Listening for iBeacons...
388: ad0249b25eaf458fba702d487818ce2f | 006f | 8241
768: ad0249b25eaf458fba702d487818ce2f | 006f | 8241
2750: ad0249b25eaf458fba702d487818ce2f | 006f | 8241
3086: ad0249b25eaf458fba702d487818ce2f | 006f | 8241
3822: a495deadc5b14b44b5121370f02d74de | beef | cafe <-- Bean!
3989: a495deadc5b14b44b5121370f02d74de | beef | cafe <-- Bean!
4846: ad0249b25eaf458fba702d487818ce2f | 006f | 8241
5403: ad0249b25eaf458fba702d487818ce2f | 006f | 8241
```

The script searches for iBeacons that match the following pattern (`_` can be any value):

```
a495____c5b14b44b5121370f02d74de
```

If it finds a matching iBeacon, it marks it as a [LightBlue Bean](http://punchthrough.com/bean).

Since Beans can only set those 16 bits of their iBeacon UUID, they will always match the above pattern. However, nothing stops other iBeacons from using a similar UUID and being marked as Beans.

This script is known to work with Node 5.1.1 on OS X 10.11.1.

# License

MIT
