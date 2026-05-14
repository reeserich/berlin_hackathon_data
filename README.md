## Article datasets and lists

The processed article-level datasets have the following fields:

`source`: describes the dataset (e.g., "pps_tortured")
`doi`: provides the DOI of the article, converted to lowercase.
`notes`: provides additional context if provided by the original dataset.
`dim_id`: If provided by the source dataset, provides the Dimensions identifier of the article (pubid, specific to PPS datasets).

### Retraction Watch Database (rwdb)

Retracted articles from the Retraction Watch Database.
Original data in `data/260513_rwdb/`. Processed data just for rwdb in `260513_rwdb.csv`.
Downloaded 13 May 2026 from https://gitlab.com/crossref/retraction-watch-data/-/blob/main/retraction_watch.csv?ref_type=heads.
Processed data only includes Retraction events (see `RetractionNature`) column. `notes` field contains annotated reasons for retraction. `doi` keeps original article's DOI, not the retraction notice DOI.

### Problematic Paper Screener (pps)

Articles identified by various detectors in the Problematic Paper Screener.
Original data in `data/260513_pps/`. Processed data just for pps in `260513_pps.csv`.
Downloaded 13 May 2026 from each of ten detectors at https://www.irit.fr/~Guillaume.Cabanac/problematic-paper-screener/ (last updated 9 May 2026).
`notes` column contains fingerprint information for each detector (for instance, the Feet of Clay detector has the `Cited Problematic Papers` field in this column.)

### Aggregated Corpora for Richardson et al., PNAS 2025 (aggregate_corpora)

An aggregated dataset of likely and confirmed paper mill products from Richardson et al., "The entities enabling scientific fraud at scale are large, resilient, and growing rapidly", PNAS 2025.
Original data in `data/260513_aggregate_corpora/`. Processed data just for this dataset in `260513_aggregate_corpora.csv`.
Downloaded from Dataset S2 of https://doi.org/10.1073/pnas.2420092122. Dataset S1 provides a key describing each of the consistuent corpora of likely or confirmed paper mill products (also available in `data/260513_aggregate_corpora/pnas.2420092122.sd01.xlsx`).
`notes` column describes the constituent dataset from which the DOI was sourced.

### Pandora's Box confirmed paper mill products, Abalkina et al., arXiv 2026 (pandora)

A corpus of strongly-implicated paper mill products, primarily in conference proceedings, from Abalkian et al., ""

## Indexing datasets and journal lists

A combined dataset containing all of the indexing datasets and journal lists described below is available as `260513_combined_journal_level_datasets`. The processed journal-level indexing datasets have the following fields:

`service`: Then name of the database or journal list (WoS, Scopus, etc).
`edition`: Either describes the download data of the information (e.g., for wos, scopus) or the edition of the journal list (e.g., the 2022 ADBC list)
`internal_identifier`: If an internal identifier for the journal (other than the journal name) is provided, it appears here.
`journal_title`: Title of the journal as it appears in the database or journal list.
`p_issn`: print ISSN (see caveats below).
`e_issn`: electronic/online ISSN (see caveats below).
`indexing_status`: whether the journal is current indexed or deindexed in the database.
`notes_on_indexing_status`: provides additional context specific to each dataset.

### Web of Science indexing data (wos)

Original data in `/data/260513_wos_cc/`. Processed data for just WoS is in `260513_wos_cc.csv`.
Original data downloaded from WoS (https://mjl.clarivate.com/collection-list-downloads) on 13 May, 2026 (last updated 20 April 2026, according to Clarivate), is stored in `/data/260513_wos_cc/`. The processed indexing data only shows journals currently indexed or journals listed in the 2023, 2024, 2025 or 2026 journal change archives as "Editorially De-listed". Journals may be listed as indexed multiple times if they are in multiple WoS core collection indices (AHCI, SCIE, SSCI, ESCI).

### Scopus indexing data (scopus)

Original data in `data/260513_scopus/`. Processed data for just Scopus in `260513_scopus.csv`.
Original data downloaded from Scopus (https://www.elsevier.com/products/scopus/content) on 13 May 2026. The processed indexing data includes both journals and serial conference proceedings. Scopus provides two reasons for de-indexing: "Discontinuation" and "Journal change policy". Both of these are included in the processed data.

### DOAJ (doaj)

Original data in `data/260513_doaj/`. Processed data for just DOAJ in `260513_doaj.csv`.
Current indexing data downloaded from DOAJ (from https://doaj.org/, under Data > Journal CSV) on 13 May 2026.
Past indexing data downloaded from https://docs.google.com/spreadsheets/d/183mRBRqs2jOyP0qZWXN8dUd02D4vL0Mov_kgYF8HORM/edit and https://docs.google.com/spreadsheets/d/1Kv3MbgFSgtSDnEGkA2JacrSjunRu0umHeZCtcMeqO5E/edit on 13 May 2026.
Only journals listed as deindexed by DOAJ for the reason "Journal not adhering to best practice" are included in the processed data. For the deindexed journals, only one ISSN is provided--it is listed under `p_issn` (this does not imply if this ISSN represented the print or electronic ISSN).

### Australian Business Deans Council Journal Quality List (adbc)

Original data in `data/260513_abdc/`. Processed data for just ABDC in `260513_abdc.csv`.
Downloaded on 13 May 2026 from https://abdc.edu.au/abdc-journal-quality-list/.
Indexing levels are described here https://abdc.edu.au/wp-content/uploads/2025/12/ToRs-2025-JQL-Review-1225.pdf.
Six editions of the list are included in the processed data.

### Karolinska Institutet Journal List (kijl)

Original data in `data/260513_kijl/`. Processed data for just KIJL in `260513_kijl.csv`.
Downloaded on 13 May 2026 from https://staff.ki.se/research-support/karolinska-institutet-journal-list-kijl.
Journals graded at Level 0 are considered deindexed in the processed data.
The first edition of the list (2026) is included in the processed data.

### Publication Forum (Finland) (jufo)

Original data in `data/260513_jufo/`. Processed data for just JUFO in `260513_jufo.csv`.
Downloaded on 13 May 2026 from https://jfp.csc.fi/jufoportal ("Export Results").
The processed data includes serials and conference proceedings, but not book publishers. Journals without an assigned level are excluded.
Journals graded at Level 0 ("Other identified publication channels") in the 260513 edition are consdiered deindexed in the processed data. 
The columns `ISSNL` and `ISSN2` are mapped to `p_issn` and `e_issn` (this does not imply if this ISSN represented the print or electronic ISSN). Note that this ignores the column `ISSN1`.

### Retraction Watch Hijacked Journal Checker (rw_hjc)

Original data in `data/260513_rw_hjc/`. Processed data for just JUFO in `260513_rw_hjc.csv`.
Downloaded on 13 May 2026 from https://retractionwatch.com/the-retraction-watch-hijacked-journal-checker/.
The `p_issn` and `e_issn` columns show the ISSNs used by the hijacked journal and do not necessarily reflect if the ISSN is print or electronic. The `notes_on_indexing_status` column contains the original ISSNs.

### Chinese Academy of Sciences Journal Early Warning List (cas_ewl)

Original data in `data/260513_cas_ewl/`. Processed data for just CAS EWL in `260513_cas_ewl.csv`.
Downloaded from https://ewl.fenqubiao.com/#/en/introduction by importing into Excel on 13 May 2026.
Five editions of the list are included in the processed data. Each list includes either zero or one ISSNs per journal--these are listed in the column `p_issn` if available (this does not imply if this ISSN represented the print or electronic ISSN).