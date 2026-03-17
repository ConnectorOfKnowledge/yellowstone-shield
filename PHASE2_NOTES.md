# Yellowstone Shield - Phase 2: Public Release Roadmap

Notes from Gemini collaboration (March 16, 2026) for expanding this into a public road trip app.

## Target Audience
Standard road-trippers + RV/Skoolie nomad community

## Features to Build

### Off-Grid & Campgrounds
- Free dispersed camping (BLM land, National Forests)
- Established campgrounds with filter/sort

### Utility Stops
- Potable water fill-ups (prioritize high-flow hookups like truck stops over park spigots)
- Dump stations with free vs. paid visual distinction

### Oversized Vehicle Routing (Critical for RV/Skoolie)
- Bridge and tunnel clearance warnings (flag anything under 12 feet for 11-foot Skoolie safety buffer)
- Elevation profiles and grade warnings (flag grades exceeding 6%, mountain passes, cliff exposures)
- Routing rule: avoid unpaved roads during transit, limit to final approach to campsite (under 10 miles)

### Fuel System
- Toggle between Regular Gas and Diesel
- Fuel price integration (see API notes below)

## API & Data Strategy

### Current (Free/Open Source)
- **OpenStreetMap (Overpass API):** Fuel types, dump stations, water points, bridge clearances
- **USFS + BLM Public GIS:** Dispersed camping boundaries
- **Fuel prices:** Skip pricing for now unless easy free API found

### Future Scaling (Paid/Premium)
- **TomTom or HERE Routing APIs:** Enterprise-grade truck/RV routing (grade, weight, clearance data)
- **GasBuddy / OPIS:** Real-time fuel pricing

## Architecture Decisions Needed
1. Database schema updates for new location types + gas/diesel user setting
2. Overpass API query design for Phase 1 amenities
3. Decision: pull OSM data on-the-fly (viewport/route based) vs. cache in backend
