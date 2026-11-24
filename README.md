# Live Location Tracker

A Node.js, Express, and Socket.IO demonstration that receives shared GPS
coordinates and updates a map in real time.

## Scope and attribution

The project is intended for consent-based demonstrations of location sharing.
Use it with participants who understand what is collected and who can view it.
The existing README referenced
[madhanmaaz/live-location-tracker](https://github.com/madhanmaaz/live-location-tracker);
that reference is retained as upstream attribution.

This project does not have a hosted demo. The included [Render configuration](render.yaml)
defines a deployment recipe, rather than proof of a currently hosted instance.

## Run locally

The package declares Node.js 16 or newer. Install Node.js and npm, then:

```bash
git clone https://github.com/dishitabuilds/Location-tracker.git
cd Location-tracker
npm install
npm start
```

Open [http://localhost:6589](http://localhost:6589), unless you set a different
`PORT`. Stop the server with Ctrl+C.

## Configuration

[config.js](config.js) reads `PORT`, `USERNAME`, `PASSWORD`, and `TOKEN` from the
process environment. Configure the login values and a fresh random token before
a shared deployment. This application does not load a `.env` file itself.

The checked-in fallback login is `admin` / `admin`; it is for local demonstration.
Coordinates are held in memory and are lost when the process restarts. Location
submission and Socket.IO access need further hardening before use with real users.

## Structure

- [server.js](server.js): Express, HTTP, and Socket.IO startup.
- [router.js](router.js): login, location submission, and map routes.
- `views/` and `public/`: pages and browser assets.
- [render.yaml](render.yaml): Render service configuration.

The `npm run dev` script invokes nodemon, which is not declared in the package
dependencies. Use `npm start` for the documented setup.

## Verification

No automated test suite is committed in this repository. Check startup, login,
and location updates with consenting test participants before demonstrating it.
