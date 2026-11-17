# Buildings

This folder contains the current Overture Maps building-data workflow for the City Digital Twin.

The workflow maps Overture building fields to the City Digital Twin / ISO/IEC ontology patterns, converts the data to RDF/Turtle, clips the source data to the Toronto boundary, records provenance, and validates the generated output.

## Structure

- **Mappings/** - current Overture building ontology mapping.
- **Scripts/** - production Overture-to-RDF conversion script.
- **Samples/** - small source/output examples for reproducibility.
- **Metadata/** - Overture release/download state metadata.
- **Validation/** - validation results from sample and full Toronto runs.

The boundary file used for clipping is `neighbourhoods-historical-140-4326.geojson`, maintained with the Administrative Areas/source work and in the standalone Building repository.

## Full Toronto run

- Overture release: **2026-10-21.0**
- Input building features: **569,053**
- Toronto buildings retained: **427,762**
- Features excluded outside Toronto: **141,291**
- RDF triples written: **7,665,615**
- First Canadian Place validation: **PASS**

The production source file `toronto_buildings_full.geojsonseq` and generated `toronto_overture_buildings_full.ttl` are intentionally not stored here because of their size.
