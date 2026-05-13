Space Janitor — Orbital Debris Mission Planner
Live app → veercnyc-git.github.io/space-janitor
A web app that helps space agencies plan optimal debris removal missions in Low Earth Orbit. Built by 8th graders for a Geometry final project.

What it does:
Space debris is a growing crisis — there are 27,000+ tracked objects in orbit, and if the density gets too high, a single collision could trigger a chain reaction that makes entire orbital shells unusable for generations (called Kessler Syndrome).
Space Janitor lets you:

Add debris objects by name or NORAD ID from a catalog of 27,000+ tracked objects
Visualize their orbits on an interactive 3D globe with real altitude and inclination data
Generate an AI mission plan that calculates the optimal collection sequence and launch window using Hohmann transfer math


How it works
The Math — Hohmann Transfers
To move between two orbits with minimum fuel, spacecraft use a Hohmann transfer: two engine burns tracing an elliptical arc. The delta-v (fuel cost) is:
Δv₁ = √(μ/r₁) × (√(2r₂/(r₁+r₂)) − 1)
Δv₂ = √(μ/r₂) × (1 − √(2r₁/(r₁+r₂)))
Where μ = 3.986×10¹⁴ m³/s² (Earth's gravitational parameter). The AI scores every possible collection ordering using these equations and finds the cheapest total route.
The Data:
Orbital parameters (altitude, inclination, eccentricity) come from Celestrak's GP catalog, maintained by Dr. T.S. Kelso — the standard reference used by space agencies worldwide.
The Globe:
The 3D globe shows each object's correct orbital shell — real altitude and inclination from Celestrak data. Built with Three.js and a procedural Earth texture.

Tech stack
LayerTechnologyFrontendHTML, CSS, JavaScript3D GlobeThree.jsOrbital dataCelestrak GP catalogAI mission plannerOpenAI GPT-4o-miniAPI proxyCloudflare WorkersHostingGitHub Pages

Try it

1. Go to the Mission Planner tab
2. Click any of the quick-add chips (Envisat, Fengyun 1C, etc.) or type a NORAD ID
3. Add at least 2 objects
4. Set a launch window and click Calculate mission plan


Built by
8th graders applying orbital mechanics, graph optimization, and AI to a real engineering problem.
Orbital Mechanics Hohmann Transfers Kessler Syndrome Three.js OpenAI
