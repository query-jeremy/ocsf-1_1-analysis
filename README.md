# Artifacts for analyzing the impact of upgrading QDM to OCSF v1.1

## Assumptions:

 - We'll change how extensions are handled so that the `macos`, `linux`, and `win` extensions work.
 - We'll use the [qdm-curator](https://github.com/query-ai/qdm-curator/tree/initial) process to preserve record types and attributes to minimize the change.
 - By OCSF v1.1, we mean `ocsf-schema/main@d65578dc77231d34673939327666b4643f6cae9a`. An official tagged release of OCSF v1.1 has not yet been christened.

## Artifacts

 - `comparison.md`: This compares QDM to OCSF. It lists the record types in use in QDM today, those which cannot show up in search results, those which _would_ be removed in a pure upgrade, and those which need references updated for new extension rules.
 - `curator.log`: The output of running the `qdm-curator` process for this upgrade. It lists nearly 5,000 changes to patch OCSF 1.1 to remain backwards compatible with QDM.
 - `curate.toml`: The configuration file used by the curation process above.
 - `deprecated/`: The output of the curation process. The contents of this extension are meant to be merged into the core schema, adding to and replacing the core definitions. The `ocsf-utils` package already handles this merging of extensions when properly configured. **NOTE**: ignore anything from the query extension - I forgot to include it alongside OCSF 1.1 when running the process.
