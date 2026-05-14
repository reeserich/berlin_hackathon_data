## Journal indexing datasets

The processed journal indexing datasets have the following fields:

`service`: Then name of the database or journal list (WoS, Scopus, etc).
`internal_identifier`: If an internal identifier for the journal (other than the journal name) is provided, it appears here.
`journal_title`: Title of the journal as it appears in the database or journal list.
`p_issn`: print ISSN.
`e_issn`: electronic/online ISSN.
`indexing_status`: whether the journal is current indexed or deindexed in the database.

### Web of Science indexing data (wos)

Original data in `/data/260513_wos_cc/`. Processed data for just WoS is in `260513_wos_cc.csv` and `260513_wos_cc.parquet`.
Original data downloaded from WoS (https://mjl.clarivate.com/collection-list-downloads) on 13 May, 2026 (last updated 20 April 2026, according to Clarivate), is stored in `/data/260513_wos_cc/`. The processed indexing data only shows journals currently indexed or journals listed in the 2023, 2024, 2025 or 2026 journal change archives as "Editorially De-listed".

### Scopus indexing data (scopus)

Original data in `data/260513_scopus`. Processed data for just Scopus in `260513_scopus.csv` or `260513_scopus.parquet`.
Original data downloaded from Scopus (https://www.elsevier.com/products/scopus/content) on 13 May 2026 is stored in `/data/260513_scopus/`. The processed indexing data includes both journals and serial conference proceedings. Scopus provides two reasons for de-indexing: "Discontinuation" and "Journal change policy". Both of these are included in the processed data.

### DOAJ (doaj)

Original data in `data/260513_doaj/`. 
Current indexing data downloaded from DOAJ (from https://doaj.org/, under Data > Journal CSV) on 13 May 2026.
Past indexing data downloaded from https://docs.google.com/spreadsheets/d/183mRBRqs2jOyP0qZWXN8dUd02D4vL0Mov_kgYF8HORM/edit and https://docs.google.com/spreadsheets/d/1Kv3MbgFSgtSDnEGkA2JacrSjunRu0umHeZCtcMeqO5E/edit on 13 May 2026.
Only journals listed as deindexed by DOAJ for the reason "Journal not adhering to best practice" are included in the processed data. For the deindexed journals, only one ISSN is provided--it is listed under `p_issn`.

### Chinese Academy of Sciences Journal Early Warning List (2025)