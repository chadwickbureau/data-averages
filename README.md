# (Experimental) repository of transcribed historical baseball statistics

This repository contains representations of statistical and related data for
historical (non-Major League) baseball leagues, from various sources.

Important preliminaries:
* These are data on historical minor professional leagues and other leagues, not
  Major Leagues (or top international leagues).
* These are **transcriptions**.  They attempt to render exactly the content of
  the original source while marking the content up in a standard structure.
  If the original source contains errors or inconsistencies, these also appear in
  these files.  The data at this stage are not normalised - there are no primary
  or foreign keys representing people, teams, leagues, etc.
* Therefore, this is not a resource intended
  for end-user consumption, and you should not use data from this repository for
  analytical purposes or quote it in research papers, blog posts, and so on.
  
That is to say, these are the raw data that are intended as initial input into
a data pipeline which cleans, edits, and normalises the data.

For the most part, the data captured here are data from league-level statistical
reports.  These may be official or pseudo-official (such as averages published
in Guides), statistical tabulations published in newspapers, or tabulations made
by individual researchers.  Each source is conceptualised as a collection of
tables, where each table consists of one type of data (for example, playing
statistics for a team, playing statistics for individual people, managing records
for individual people).  The representation balances two considerations:
* The tables attempt, to the extent possible, to reproduce the structure of the
  tables in the source.  Rows and columns in the transcription should be in the
  same order as those in the source.  This is useful for humans cross-checking
  data against the source to identify transcription errors.
* The tables identify columns in the source by standard category abbreviations, so
  differences across sources in labeling the "same" statistical category are
  irrelevant.
Therefore, enough standardisation is done to help downstream consumers of these files
from having to figure out the semantics of different fields, while at the same time
relevant details about the structure of the original document are also retained and
encoded, as in some cases knowledge about that structure can be useful.  For example,
some league averages have multiple tables containing batting statistics, one table
with the "main" categories and other subtables with breakouts of "lesser" categories.
This format can represent these as multiple tables, which downstream processors can
use to know that the same person is being referenced in multiple tables - whereas it
is less likely the same person is referenced twice in the same table (except in the
case of an error).

The averages are grouped by source (e.g. a particular edition of a Guide) or
source type (e.g. newspapers in general).  Within each group, each league's statistics
are treated as a separate package.


## Contact

For more information on the format or the capture of this data, contact
Ted Turocy at Chadwick Baseball Bureau (ted.turocy@gmail.com).
