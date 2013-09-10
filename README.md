<b>MetPlus DB</b>

Description:
---------------------
MetPlus DB as a standalone SQLite database is developed to facilitate external identifier or mass-based searches from the collection of comprehensive metabolite databases. The data is primarily integrated by merging records based on IUPAC International Chemical Identifier (InChIKey) to deliver high confidence annotations with a significantly reduced redundancy and eliminates the complexity of extracting metabolite annotations from individual databases.

Disclaimer:
---------------------
MetPlus DB is a freely accessible SQLite database that assembles information from 3rd party data sources. We cannot guarantee that the database is error-free. Please feel free to report an error or send comments/suggestions to corresponding author by e-mail. We shall not be held liable for any inaccuracies and/or misuse of the information provided. Database updates take place every quarterly to broaden the search space and accommodate additional data-fields to serve the scientific community with the most up-to-date and comprehensive information on metabolites.

Usage:
------

1) Loading Sqlite Database

sqlite3 Metplus.db

2) Look-up Database Schema

.schema MetPlus

Result:

CREATE TABLE MetPlus
(INCHIKEY VARCHAR(30),
FORMULA VARCHAR(30),
MONOISOTOPIC_WEIGHTS REAL,
COMMON_NAME VARCHAR(100),
IUPAC_NAME VARCHAR(500),
SYSTEMATIC_NAME VARCHAR(500),
TRADE_NAME VARCHAR(500),
HMDB_ID VARCHAR(30),
LMDB_ID VARCHAR(30),
HUMANCYC_ID VARCHAR(20),
PUBCHEM_CID INT,
CHEMSPIDER_ID INT,
CHEBI_ID INT,
METLIN_ID INT,
KEGG_ID VARCHAR(30),
FooDB_ID VARCHAR(30));

2) Running SQL query to output first 2 rows from MetPlus-DB

select * from MetPlus limit 2;

Result:

inchikey,monoisotopic_weight,formula,common_name,iupac_name,systematic_name,trade_name,HMDB_id,
LMDB_id,Humancyc_id,Pubchem_CID,Chemspider_id,Chebi_id,metlin_id,KEGG_id,foodb_id

AAABYGXUNQSIIU-IOWSJCHKSA-N,652.431535,C33H65O10P,PG(13:0/14:0),[(2R)-1-[[(2S)-2,3-dihydroxypropoxy]-hydroxyphosphoryl]oxy-3-tridecanoyloxypropan-2-yl] tetradecanoate,[(2R)-1-[[(2S)-2,3-bis(oxidanyl)propoxy]-oxidanyl-phosphoryl]oxy-3-tridecanoyloxy-propan-2-yl] tetradecanoate,myristic acid [(1R)-1-[[[(2S)-2,3-dihydroxypropoxy]-hydroxy-phosphoryl]oxymethyl]-2-tridecanoyloxy-ethyl] ester,NA,LMGP04010069,NA,52926334,NA,NA,NA,NA,NA

AAAFZMYJJHWUPN-AIHAYLRMSA-J,305.954184,C5H8O11P2-4,D-ribose 1,5-diphosphate,[(2S,3R,4S,5R)-3,4-dihydroxy-5-(phosphonatooxymethyl)oxolan-2-yl] phosphate,[(2S,3R,4S,5R)-3,4-bis(oxidanyl)-5-(phosphonatooxymethyl)oxolan-2-yl] phosphate,[(2S,3R,4S,5R)-3,4-dihydroxy-5-(phosphatomethyl)tetrahydrofuran-2-yl] phosphate,NA,NA,hum0001,25244507,2300618,1044,111293,388533,26328792,26331130,NA,NA,NA,NA

3) Running SQL query to look up anntations for Glycerol

select * from MetPlus where COMMON_NAME = 'Glycerol';

Result:

inchikey,monoisotopic_weight,formula,common_name,iupac_name,systematic_name,trade_name,HMDB_id,
LMDB_id,Humancyc_id,Pubchem_CID,Chemspider_id,Chebi_id,metlin_id,KEGG_id,foodb_id

PEDCQBHIVMGVHV-UHFFFAOYSA-N,92.047344,C3H8O3,Glycerol,propane-1,2,3-triol,propane-1,2,3-triol,glycerol,HMDB00131,NA,hum0691,753,733,17522,17754,105,C00116,FDB000756



