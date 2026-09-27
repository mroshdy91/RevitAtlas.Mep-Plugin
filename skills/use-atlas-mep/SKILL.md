---
name: use-atlas-mep
description: Use Atlas MEP with Atlas Core for the qualified piping and mechanical equipment scope in owned Revit 2025 or 2026 projects, including connected work, drawing review and saved RVT verification.
---

# Atlas MEP: piping and equipment scope

Atlas MEP uses the shared Atlas Core runtime. The installed release admits an explicit list of MEP actions for Revit 2025 and 2026. Read `RELEASE-READINESS.json` and the current `atlas_catalog` action contract before a call; tool discovery alone does not qualify an action. Electrical, spaces, ductwork, containment, shared setup changes and arbitrary project editing are outside this scope. Atlas Family owns loadable family authoring.

Start with `atlas_status`, select the live Revit session, and create or open an owned standalone project through Core. Inspect existing content and capture the engineering brief with `atlas_requirements`. Workshared and cloud writes are unavailable. Reinspect native identities after changing a component or route; use current work revisions, observed connector handles and explicit units.

The admitted MEP actions are `atlas_mep_routes.plan`, `atlas_mep_routes.build`, `atlas_mep_elements.load`, `atlas_mep_elements.place`, `atlas_mep_elements.move`, `atlas_mep_connections.join`, and `atlas_mep_setup.inspect`. Core also admits `atlas_inspect.mep_catalog`, `mep_network`, `mep_dependencies`, `mep_plan`, `mep_preservation`, and `atlas_validate.mep`. Other actions, including insulation and removal, are not admitted in this release.

Route plans must specify `kind: pipe`; build only a retained current pipe plan. Loaded and placed content must resolve to pipe-only mechanical equipment or pipe accessory, and connections must resolve to the piping domain. Select actual project content; do not invent type, connector or fitting identities.

Use Core `atlas_inspect` to check catalog content, physical ports, network edges, dependencies and preservation. A visual touch or connector reference alone does not establish a physical connection. For connected edits, inspect affected neighbours and declare only engineering-intended `allowed_changes`. Read committed, rolled-back or uncertain outcomes; recover the original operation identity before retrying. Keep unrelated model elements, host relationships and source files intact.

Record measurable requirements and validate the admitted MEP criteria. Use Sheets and Annotations for project drawings when those specialists are installed, then review actual tags, schedules, sheet content and visual output. Core owns saved RVT delivery and reopening checks. A connectivity pass, drawing export or saved file alone does not certify the whole brief; report remaining engineering or visual checks explicitly.
