# City Digital Twin Ontology

The City Digital Twin project at the University of Toronto's Urban Data Research Centre develops a standards-based knowledge graph for City of Toronto data. The project uses Linked Data and city-data standards including ISO/IEC 21972 and ISO/IEC 5087.

This repository contains mappings, transformation scripts, ontologies, diagrams, and project documentation used to build and maintain the City Digital Twin.

## Repository organization

Active work is organized primarily by subject/domain:

- **Administrative Areas/** - Toronto administrative-area mappings, scripts, diagrams, and validation.
- **Buildings/** - building mappings and RDF generation scripts, including the current Overture Maps workflow.
- **Census/** - census mappings, transformation scripts, and documentation.
- **Services and Amenities/** - services and amenities mappings, including OpenStreetMap-based transformation scripts.
- **Ontologies/** - shared ontology files used across City Digital Twin domains.
- **Documentation/** - project-wide manuals, presentations, and Toronto Common Data Model documentation.
- **Housing Potential Project/** - historical Housing Potential project material.

## Reorganization status

The repository is being migrated from its older mixed layout to the subject-oriented structure above. During the transition, legacy folders remain in place so that historical content is not lost and duplicate/current files can be reviewed before anything is removed.

Large raw datasets should generally remain outside GitHub. Small samples may be retained when they are useful for reproducibility.
