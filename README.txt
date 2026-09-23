Open Landscape FX v0.28.0 — Safe updates and corrected distribution

This release is based on the supplied v0.27.2 source.

Fixes included:

1. OLFUPDATE now rebuilds existing schedules transactionally. Existing schedule tables are not erased until replacement tables have been appended successfully. If no schedule exists, OLFUPDATE does not create one and leaves the drawing unchanged. Existing linked labels are updated only; unlabeled plants are not labeled.

2. OLFPLANTSCHEDULE ensures the configured Schedule Layer before assigning tables to it, preventing failures when the project uses a custom layer name.

3. Area distribution no longer anchors the grid to an arbitrary picked start point. The grid is centered on the selected boundary extents and explicitly includes the final half-spacing sample, so a rectangle with a non-multiple width or height does not lose the remaining strip. Area symbols use one uniform scale per run based on the closest candidate-center distance.

4. Path distribution collects all path points before insertion and calculates one uniform scale from the actual points. This prevents overlapping canopies on straight and closed rectangular paths while preserving the requested center spacing.

5. Plant Data Manager Update and Duplicate preserve Water Requirement, Sun Requirement, Maintenance, Notes, Symbol Name, and Symbol Version. CSV import/export now handles quoted fields and commas in names or notes.

6. Invalid plants.json files are backed up and reported instead of being silently ignored. OLFABOUT reports version 0.28.

7. A configured SymbolName is used as the stable block definition name when creating or replacing a plant. Existing blocks are not automatically migrated by this release; a dedicated migration command remains the next step.

Build target: AutoCAD 2021 API. Build succeeded with the existing obsolete Table API warnings.

Installation: close AutoCAD, NETLOAD OpenLandscapeFx-v0.28.dll, then run OLF.
