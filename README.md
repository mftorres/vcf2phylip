# vcf2phylip
Convert SNPs in VCF format to PHYLIP for phylogenetic analysis

## _Brief description_
The script converts a collection of SNPs in VCF format into a PHYLIP file for phylogenetic analysis. In case of heterozygous SNPs the IUPAC ambiguity code is used to construct the final DNA sequence. Once the PHYLIP file is obtained , conversion to other alignment formats (e.g. FASTA) is trivial with other software like [Aliview](http://ormbunkar.se/aliview/).

A minimum number of samples per SNPs can also be specified so you won't need to run again the software that created your VCF file just to increase this threshold.

The script has been tested with VCF files produced by [pyrad v.3.0.66](https://github.com/dereneaton/pyrad), [ipyrad](http://ipyrad.readthedocs.io/), and [Stacks v.1.47](http://catchenlab.life.illinois.edu/stacks/), but might work with VCFs from GATK as well.

## _Usage_
Simply specify the name of the VCF input file and optionally the minimum of samples per SNP (default 4 for phylogenetics):

_Example 1:_ Using the default minimum of samples per SNP of 4:
```bash
python vcf2phylip.py myfile.vcf
# This command will create a PHYLIP called myfile_min4.phy
```

_Example 2:_ Using a custom minimum of samples per SNP of 64:
```bash
python vcf2phylip.py myfile.vcf 64
# This command will create a PHYLIP called myfile_min64.phy
```
