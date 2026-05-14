## Indexing datasets and journal lists

The processed journal indexing datasets have the following fields:

`service`: Then name of the database or journal list (WoS, Scopus, etc).
`edition`: Either describes the download data of the information (e.g., for wos, scopus) or the edition of the journal list (e.g., the 2022 ADBC list)
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

Original data in `data/260513_doaj/`. Processed data for just DOAJ in `260513_doaj.csv` or `260513_doaj.parquet`.
Current indexing data downloaded from DOAJ (from https://doaj.org/, under Data > Journal CSV) on 13 May 2026.
Past indexing data downloaded from https://docs.google.com/spreadsheets/d/183mRBRqs2jOyP0qZWXN8dUd02D4vL0Mov_kgYF8HORM/edit and https://docs.google.com/spreadsheets/d/1Kv3MbgFSgtSDnEGkA2JacrSjunRu0umHeZCtcMeqO5E/edit on 13 May 2026.
Only journals listed as deindexed by DOAJ for the reason "Journal not adhering to best practice" are included in the processed data. For the deindexed journals, only one ISSN is provided--it is listed under `p_issn` (this does not imply if this ISSN represented the print or electronic ISSN).

### Chinese Academy of Sciences Journal Early Warning List (cas_ewl)

Original data in `data/260513_cas_ewl`. Processed data for just CAS EWL in `260513_cas_ewl.csv` or `260513_cas_ewl.parquet`.
Downloaded from https://ewl.fenqubiao.com/#/en/introduction by importing into Excel.
Five editions of the list are included in the processed data. Each list includes either zero or one ISSNs per journal--these are listed in the column `p_issn` if available (this does not imply if this ISSN represented the print or electronic ISSN).

### Australian Business Deans Council Journal Quality List (adbc)

Original data in `data/260513_abdc`. Processed data for just ABDC in `260513_abdc.csv` or `260513_abdc.parquet`.
Indexing levels are described here https://abdc.edu.au/wp-content/uploads/2025/12/ToRs-2025-JQL-Review-1225.pdf.
Six editions of the list are included in the processed data.