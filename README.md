# SpatialGH_InverseDesign

This is the companion software repo for our paper on floorplan inverse design. It ships as a Grasshopper plugin (`SpatialGH_InverseDesign.zip`) plus an example definition (`InverseDesign_example.gh`) and the data it relies on (`database/`).

## Installation

1. **Find your Grasshopper components folder.** In Rhino, open Grasshopper, then go to `File > Special Folders > Components Folder`. This is normally:
   ```
   %APPDATA%\Grasshopper\Libraries
   ```
   (i.e. `C:\Users\<you>\AppData\Roaming\Grasshopper\Libraries`).

2. **Unzip the plugin there.** Extract `SpatialGH_InverseDesign.zip` directly into that `Libraries` folder, so you end up with:
   ```
   Libraries\SpatialGH_InverseDesign\SpatialGH.gha
   Libraries\SpatialGH_InverseDesign\... (dependency DLLs)
   ```

3. **Unblock the files if needed.** If the zip was downloaded from the web, Windows may flag the `.gha`/`.dll` files as blocked. Right-click `SpatialGH.gha` (and the DLLs, if Grasshopper complains) → Properties → check "Unblock" → OK.

4. **Restart Rhino/Grasshopper.** The plugin's components should now appear on the Grasshopper ribbon.

## Setting the database path

The example definition (`InverseDesign_example.gh`) needs to know where the data lives:

1. Open `InverseDesign_example.gh` in Grasshopper.
2. Find the input that points to the database folder (a path/string input feeding the plugin's database-loading component).
3. Set it to the `database/` folder of **this** repo, given as a folder path (not a specific file inside it), e.g.:
   ```
   E:\Projects\26Summer_Spatial\SpatialGH_InverseDesign\database
   ```

The `database` folder contains:
- `database.json` — the floorplan database
- `test.json` — test split
- `boundary_score.json`, `srds_score.json` — precomputed scores used by the components

Once the path is set, the definition should run end to end.

## Troubleshooting

- **Many components show errors:** re-activate the plugin license.
- **Components still show errors after re-activating the license:** right-click on the canvas (or the affected component) → **Recompute**.

## License

MIT — see [LICENSE](LICENSE).
