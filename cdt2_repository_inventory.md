# CDT2 Repository Inventory

## Baseline checked

Date checked: June 3, 2026  
Repository: CDT_HPCDM_Demo at cdt2  
Repository URL: https://cdt2.project.urbandatacentre.ca/

## Purpose

This file tracks the current contents of the duplicated CDT2 GraphDB repository, what data is already loaded, what data still needs to be added or corrected, and any mapping or named-graph issues that need follow-up.

This inventory is intended to record:

- what is currently in the repository
- what data is added later
- source data used
- mapping scripts or resources used
- target named graph
- known issues or follow-up tasks

---


## Current supervisor instructions

Based on the latest email thread, the immediate priority is no longer the missing `cdt:Amenity` class issue. That issue has been set aside because the old dashboard appears to have used an older amenity mapping approach where amenities were modeled as superclasses of services, while the newer approach was not implemented.

Current priorities:

1. Initialize the complete census data in the new `cdt2` repository.
2. Investigate the existing limited census excerpt currently loaded as `http://example.com/CensusSampleLimited.ttl`.
3. Investigate older neighbourhoods and associated census tracts stored in `http://example.com/Toronto.ttl`.
4. Identify and replace use of the old location namespace:
   `http://ontology.eil.utoronto.ca/5087/1/SpatialLoc/hasLocation`
   with the correct ISO namespace.
5. Investigate why water ward data appears in the default graph in the old CDT repository and correct this in `cdt2`.
6. Keep an inventory of current graphs, added data, source data, scripts/resources, named graphs, and notes.

## Existing named graphs

| Named graph | Approx. triples | Main contents | Notes |
|---|---:|---|---|
| `http://example.com/Buildings.nt` | 14,830,196 | Buildings, parcels, locations, addresses, building height, building use, area measures | Largest graph. Relevant for building-data and complete communities work. |
| `http://example.org/inferences` | 6,412,214 | Inferred triples | Inference graph. Not source data. |
| `http://example.com/toronto_roads` | 3,984,654 | Road network data | Contains ORN road mapping. |
| `http://example.com/SewerGravityMain.ttl` | 3,808,241 | Sewer gravity main / wastewater service data | Very large utility graph. |
| `http://example.com/ParcelPerimeter.ttl` | 2,114,308 | Parcel perimeter data | Needs source/script confirmation. |
| `http://example.com/Fakeowners.ttl` | 1,888,224 | Synthetic parcel ownership data | Synthetic/mock ownership data. |
| `http://example.com/RoadCapacities` | 1,388,900 | Road capacity / transportation service capacity | Synthetic or derived transportation capacity graph. |
| `http://example.com/Zone` | 735,576 | Zoning data | Relevant to historical/zoning work. |
| `http://example.com/NewWater` | 238,926 | Water service / water distribution / catchment area data | Check relation to water named-graph issue. |
| `http://example.com/TransitStop.ttl` | 84,247 | Transit stop data | Transit graph. |
| `http://example.com/CensusSampleLimited.ttl` | 51,408 | Limited/sample census data, census tracts, census profile 2016, population, population density, dwellings | Current census data appears to be only an excerpt. Needs replacement with complete census data. |
| `http://example.com/Height` | 40,449 | Height regulation / administrative area / building population data | Needs source/script confirmation. |
| `http://example.com/ParksCapacity.ttl` | 34,692 | Park/recreation capacity indicators | Complete communities related. |
| `http://example.com/Parks.ttl` | 33,954 | Park services, park sites, locations, area, addresses, organizations | Complete communities related. |
| `http://example.com/CACensus.ttl` | 33,163 | Census ontology/classes/properties/units | Ontology/schema graph, not the full census data itself. |
| `http://example.com/PublicSchools.ttl` | 19,973 | Public school services, school sites, elementary/secondary schools, locations, addresses | Complete communities related. |
| `http://example.com/TransitRoute.ttl` | 16,260 | Transit route / public transit service data | Transit graph. |
| `http://example.com/GTHALowerTier.ttl` | 16,142 | GTHA lower-tier parcel/location/government organization data | Administrative / parcel related. |
| `http://example.com/Childcare.ttl` | 15,121 | Childcare services, childcare sites, enrollment spaces, locations | Complete communities related. |
| `http://example.com/SupermarketCapacity.ttl` | 14,157 | Supermarket population ratio / capacity indicators | Complete communities related. |
| `http://example.com/Supermarket.ttl` | 13,056 | Supermarket services, supermarket sites, locations, addresses, organizations | Complete communities related. |
| `http://example.com/ChildcareSynthetic.ttl` | 12,960 | Synthetic childcare enrollment size / available spaces | Synthetic complete communities capacity data. |
| `http://example.com/FeederCapacity.ttl` | 11,578 | Electrical feeder capacity / available electrical capacity | Utility graph. |
| `http://example.com/PublicSchoolsCapacity.ttl` | 9,444 | School enrollment capacity / available spaces | Complete communities related. |
| `http://example.com/Toronto.ttl` | 9,324 | Toronto base geography, neighbourhoods, wards, census tracts, population centres, police divisions, locations | Important. Needs investigation for older neighbourhood and census tract mapping. Also relevant to old `hasLocation` namespace issue. |
| `http://example.com/TorontoLibraries` | 8,593 | Library services, libraries, library sites, wards, neighbourhoods, locations, addresses, floor area | Complete communities related. |
| `http://example.com/FederalBuildings.ttl` | 8,179 | Federal buildings, building use, building condition, area, locations, addresses, organizations | Building data. |
| `http://example.com/PublicSchoolsEnrollment.ttl` | 5,516 | School enrollment size, measures, time intervals/instants | Time-related school enrollment data. |
| `http://example.com/CommunityCentreCapacity.ttl` | 5,274 | Community centre client size / available spaces / capacity measures | Complete communities related. |
| `http://example.com/FeederTotal.ttl` | 4,962 | Electrical load capacity | Utility graph. |
| `http://example.com/SewerPressurizedMainCapacity.ttl` | 4,590 | Pressurized sewer capacity / water processing rates | Utility capacity graph. |
| `http://example.com/HPCDM.ttl` | 4,238 | HPCDM ontology/classes/properties/units | Ontology/schema graph. |
| `http://example.com/HeightRegulation` | 2,528 | Height regulation data | Related to zoning/height rules. |
| `http://example.com/SewerPressurizedMain.ttl` | 2,449 | Pressurized sewer main / wastewater service site data | Utility graph. |
| `http://example.com/CommunityCentre.ttl` | 2,345 | Community centre services, community centre sites, locations | Complete communities related. |
| `http://example.com/TransitSynthetic.ttl` | 2,040 | Synthetic transit data | Synthetic transit graph. |
| `http://example.com/SyntheticTorontoLibraries` | 1,600 | Synthetic library capacity / population ratio indicators | Synthetic complete communities data. |
| `http://example.com/Fire` | 1,431 | Fire emergency services, firefighter population minimum, addresses, organizations | Emergency service graph. |
| `http://example.com/Hospital.ttl` | 1,050 | Hospital services, hospital sites, locations, addresses, hospital organizations | Health service graph. |
| `http://example.com/fire_synthetic` | 840 | Synthetic fire-service data | Synthetic emergency service graph. |
| `http://example.com/SolidWasteCapacity.ttl` | 630 | Solid waste capacity / available waste processing rate / max waste processing rate | Utility capacity graph. |
| `http://example.com/ProvincialLands.ttl` | 461 | Provincial lands, parcels, locations, government organizations | Parcel/government land graph. |
| `http://example.com/TorontoHPCDM.ttl` | 263 | Toronto-specific HPCDM classes/restrictions/ontology content | Ontology/schema graph. |
| `http://example.com/NewWaterCapacity` | 261 | Water capacity / available water distribution rate | Utility capacity graph. |
| `http://example.com/SolidWaste.ttl` | 238 | Solid waste service data | Utility graph. |
| `http://example.com/ZoningSynthetic.ttl` | 238 | Synthetic zoning data | Synthetic zoning graph. |
| `http://example.com/LongTermCare.ttl` | 141 | Long-term care services, senior care service sites, beds, locations | Health/social service graph. |
| `http://example.com/LongTermCareCapacity.ttl` | 120 | Long-term care residents / available beds / capacity measures | Health/social service capacity graph. |
| `http://example.com/HospitalCapacity.ttl` | 54 | Hospital bed population ratio / available hospital bed ratio / minimum hospital bed ratio | Health capacity graph. |
| `http://example.com/GTHAUpperTier.ttl` | 11 | GTHA upper-tier parcel/location/government organization data | Very small graph. Needs confirmation. |
| `http://example.org/HPCDM.ttl` | 3 | HPCDM-related graph | Very small. Possible duplicate or mistaken graph URI. Needs confirmation. |

---

## Current repository-level class snapshot

A broad class query over the repository returned many large class counts. The largest visible classes include:

| Class | Approx. count | Interpretation |
|---|---:|---|
| `owl:Thing` | 1,038,114 | Broad inferred class membership |
| `hp:HPCDMThing` | 2,702,887 | Broad HPCDM inferred membership |
| `ns2:Measure` | 1,523,913 | Many measurement objects |
| `loc:Location` | 1,346,571 | Many location objects |
| `geo:Geometry` | 1,346,571 | Many geometry objects |
| `hp:BuildingThing` | 1,093,716 | Building-related inferred membership |
| `cityunits:Area` | 1,007,031 | Area measurements |
| `contact:Address` | 708,526 | Address objects |
| `hp:Building` | 567,353 | Building entities |
| `bdg:Building` | 567,353 | Building entities under building ontology |
| `hp:BuildingHeight` | 525,761 | Building height data |
| `hp:AdministrativeArea` | 497,918 | Administrative area data |
| `hp:Parcel` | 482,589 | Parcel data |
| `hp:Service` | 230,333 | Service entities |
| `cdt:RoadLink` | 57,873 | Road link entities |
| `cdt:Junction` | 40,667 | Road network junction entities |

Note: this query was not restricted to named graphs. It should be treated as a broad repository-level class snapshot, not as proof of what is loaded in the default graph.

---

## Important observations

### Census

`http://example.com/CensusSampleLimited.ttl` is present and contains a limited/sample census dataset. Its classes include:

- `cacensus:AverageAfterTaxIncome25Sample2016`
- `cacensus:Population2016`
- `cacensus:PopulationDensity2016`
- `cacensus:TotalPrivateDwellings2016`
- `cot:CensusTract`
- `cacensus:CensusProfile2016`
- `ns2:Population`
- `cacensus:PopulationDensityPopulation`

This matches the concern that the current census data is only an excerpt and should eventually be replaced with the complete census dataset.

### Toronto base geography

`http://example.com/Toronto.ttl` is present and contains Toronto base geography. Its visible classes include:

- `owl:NamedIndividual`
- `loc_old:Location`
- `cacensus:CensusTract`
- `cot:Neighborhood`
- `cot:Ward`
- `cacensus:PopulationCentre`
- `loc:Location`
- `cot:PoliceDivision`
- `cot:CommunityCouncil`
- `cot:CanadianCity`

This graph is important for the older neighbourhood and census tract mapping task.

### Complete communities related graphs

The repository already contains several complete-communities-related graphs, including:

- `Parks.ttl`
- `ParksCapacity.ttl`
- `PublicSchools.ttl`
- `PublicSchoolsCapacity.ttl`
- `PublicSchoolsEnrollment.ttl`
- `Childcare.ttl`
- `ChildcareSynthetic.ttl`
- `CommunityCentre.ttl`
- `CommunityCentreCapacity.ttl`
- `Supermarket.ttl`
- `SupermarketCapacity.ttl`
- `TorontoLibraries`
- `SyntheticTorontoLibraries`
- `Hospital.ttl`
- `HospitalCapacity.ttl`
- `LongTermCare.ttl`
- `LongTermCareCapacity.ttl`
- `Fire`
- `fire_synthetic`

### Utility and infrastructure graphs

The repository contains several utility and infrastructure graphs, including:

- `NewWater`
- `NewWaterCapacity`
- `SewerGravityMain.ttl`
- `SewerPressurizedMain.ttl`
- `SewerGravityMainCapacity.ttl` was not visible as a separate named graph in the current count output
- `SewerPressurizedMainCapacity.ttl`
- `SolidWaste.ttl`
- `SolidWasteCapacity.ttl`
- `FeederCapacity.ttl`
- `FeederTotal.ttl`
- `toronto_roads`
- `RoadCapacities`
- `TransitRoute.ttl`
- `TransitStop.ttl`
- `TransitSynthetic.ttl`

---

## Known issues / tasks to investigate

| Priority | Issue | Current evidence | Next action | Status |
|---:|---|---|---|---|
| 1 | Census data is limited | `CensusSampleLimited.ttl` exists with 51,408 triples | Inspect the graph, locate complete census source data and mapping script | Not started |
| 2 | Older neighbourhood and census tract mapping | `Toronto.ttl` contains `cot:Neighborhood`, `cot:Ward`, and `cacensus:CensusTract` | Inspect `Toronto.ttl` and find the original mapping script, possibly ask Anderson | Not started |
| 3 | Old `hasLocation` namespace | `Toronto.ttl` contains both `loc_old:Location` and `loc:Location` | Query all `hasLocation` predicates in `Toronto.ttl` and identify old namespace usage | Not started |
| 4 | Water ward data graph placement | `NewWater` and `NewWaterCapacity` exist, but water ward/default graph issue still needs confirmation | Query water/ward-related triples by graph and check default graph separately | Not started |
| 5 | Possible duplicate/mistaken ontology graph | Both `http://example.com/HPCDM.ttl` and `http://example.org/HPCDM.ttl` exist | Check whether the 3-triple graph is accidental or expected | Not started |
| 6 | Synthetic data inventory | Several synthetic graphs exist, including `Fakeowners.ttl`, `RoadCapacities`, `TransitSynthetic.ttl`, `fire_synthetic`, `ZoningSynthetic.ttl`, `SyntheticTorontoLibraries` | Confirm which scripts generated them and whether they should remain in cdt2 | Not started |

---

## Change log

| Date | Change | Source data | Script/resource | Named graph | Notes |
|---|---|---|---|---|---|
| June 3, 2026 | Baseline inventory started | GraphDB SPARQL queries | Manual SPARQL inspection | Multiple existing graphs | Initial inventory of 51 named graphs and major class contents |
