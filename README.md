# taxdata2taxflat
Converts an NCBI taxonomy dump ("taxdata") to a flat tsv file with columns for recognized ranks.

## How to run the program

The program is a Ruby script, requiring a reasonably recent version of `ruby`.
I think anything from 1.9 and up will work. (The default options system changed
in 1.9.)

Clone the repository and place a symlink to the `src/ruby/taxdata2taxflat`
script in a directory in your PATH variable.

Input files to the script are the `nodes.dmp` and `names.dmp` which can be
downloaded from NCBI's ftp site as part of the `taxdump.tar.gz`:

```bash
$ wget ftp://ftp.ncbi.nlm.nih.gov/pub/taxonomy/taxdump.tar.gz
```

After you've unpacked the tar ball somewhere, you generate the flat taxonomy
file like this:

```bash
$ taxdata2taxflat --verbose nodes.dmp names.dmp > taxflat.tsv
```
