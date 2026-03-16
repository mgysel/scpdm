# SHACL Shapes for the Smart City Project Data Model

This repository contains the SHACL shapes for the Smarty City Project Linked Data model described in the companion paper under review. The shapes define validation constraints and structure for a smart city project documentation and replication.

## Repository Structure

```
├── shapes/
│   ├── project.ttl                    # Smart City Project
│   ├── technical-process-step.ttl     # Technical process steps
│   ├── organizational-process-step.ttl# Organizational project phases
│   ├── resource.ttl                   # Reusable resource reference (docs, images, videos)
│   ├── manufacturer.ttl               # Manufacturer that produces the hardware and software
│   ├── software.ttl                   # Software applications
│   ├── hardware.ttl                   # Hardware devices
│   ├── location.ttl                   # Geographic location
│   └── dataset.ttl                    # DCAT-AP catalog and dataset shapes
└── haar_example/
    └── haar-instance.ttl              # Example instance: Ganzheitlicher Digitale Zwilling Haar
```

## Namespaces

The shapes use the following key namespaces:

| Prefix | URI |
|--------|-----|
| `dct` | http://purl.org/dc/terms/ |
| `dcat` | http://www.w3.org/ns/dcat# |
| `p-plan` | http://www.opmw.org/model/p-plan/ |
| `prov` | http://www.w3.org/ns/prov# |
| `schema` | https://schema.org/ |
| `sosa` | http://www.w3.org/ns/sosa/ |
| `ssn` | http://www.w3.org/ns/ssn/ |

## Shape Descriptions

| File | Target Classes | Description |
|------|---------------|-------------|
| `project.ttl` | `schema:Project`, `pv:CustomResource` | Core project metadata: identifier, title, description, themes, use cases, status, cost, timeline, partners, process steps |
| `technical-process-step.ttl` | `p-plan:Step` | Data collection, processing, simulation, and visualization activities with hardware/software/dataset inputs |
| `organizational-process-step.ttl` | `schema:QAPage` | Organizational phases (planning, stakeholder engagement) modeled as question–answer pairs |
| `resource.ttl` | `rdfs:Resource` | Attached documentation, images, or video links with type, URL, title, and description |
| `manufacturer.ttl` | `schema:Organization` | Manufacturer, referenced by hardware and software shapes |
| `software.ttl` | `schema:SoftwareApplication` | Software tools with version, license, capabilities, and observed/actuated properties |
| `hardware.ttl` | `ssn:System` | Physical devices with type, model, manufacturer, capabilities, and sensor properties |
| `location.ttl` | `dct:Location` | WGS84 coordinates and postal address |
| `dataset.ttl` | `dcat:Dataset`, `dcat:Catalog`, … | Full DCAT-AP shapes for dataset and catalog metadata |

## Haar Example

`haar_example/haar-instance.ttl` contains a complete example instance of the SCPDM for the *Ganzheitlicher Digitale Zwilling Haar* project — a smart city digital twin for traffic management developed by the municipality of Haar, Bavaria.

The instance illustrates:

- **Project metadata** — title, description, status, timeline, budget, contact point, and partners
- **Technical process steps** — three `p-plan:Step` instances covering data collection (Datenerfassung), data processing (Datenverarbeitung), and data visualization (Datenvisualisierung), each linked to their hardware, software, and dataset inputs
- **Organizational process phases** — four `schema:QAPage` instances (Initiieren, Planen, Umsetzen, Weiterdenken) capturing stakeholder engagement and project decisions as question–answer pairs
