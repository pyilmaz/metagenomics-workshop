MetaQUAST
=========

QUAST stands for QUality ASsessment Tool. The tool evaluates genome
assemblies by computing various metrics.  You can find all project
news and the latest version of the tool at `sourceforge
<http://sourceforge.net/projects/quast>`_.  QUAST utilizes MUMmer,
GeneMarkS, GeneMark-ES, GlimmerHMM, and GAGE. In addition, MetaQUAST
uses MetaGeneMark, Krona tools, BLAST, and SILVA 16S rRNA
database. See the `QUAST home page <http://quast.bioinf.spbau.ru//>`_
for more info.

To call ``metaquast.py`` we have to provide reference genomes which
are used to calculate a number of different metrics for evaluation of
the assembly. In real-world metagenomics, these references are usually
not available, of course::

  cd /vol/spool/tutorial-data
  python ~/quast-3.1/metaquast.py --threads 16 --gene-finding --meta \
  -R /vol/spool/tutorial-data/genomes/Aquifex_aeolicus_VF5.fna,\
  /vol/spool/tutorial-data/genomes/Bdellovibrio_bacteriovorus_HD100.fna,\
  /vol/spool/tutorial-data/genomes/Chlamydia_psittaci_MN.fna,\
  /vol/spool/tutorial-data/genomes/Chlamydophila_pneumoniae_CWL029.fna,\
  /vol/spool/tutorial-data/genomes/Chlamydophila_pneumoniae_J138.fna,\
  /vol/spool/tutorial-data/genomes/Chlamydophila_pneumoniae_LPCoLN.fna,\
  /vol/spool/tutorial-data/genomes/Chlamydophila_pneumoniae_TW_183.fna,\
  /vol/spool/tutorial-data/genomes/Chlamydophila_psittaci_C19_98.fna,\
  /vol/spool/tutorial-data/genomes/Finegoldia_magna_ATCC_29328.fna,\
  /vol/spool/tutorial-data/genomes/Fusobacterium_nucleatum_ATCC_25586.fna,\
  /vol/spool/tutorial-data/genomes/Helicobacter_pylori_26695.fna,\
  /vol/spool/tutorial-data/genomes/Lawsonia_intracellularis_PHE_MN1_00.fna,\
  /vol/spool/tutorial-data/genomes/Mycobacterium_leprae_TN.fna,\
  /vol/spool/tutorial-data/genomes/Porphyromonas_gingivalis_W83.fna,\
  /vol/spool/tutorial-data/genomes/Wigglesworthia_glossinidia.fna \
  -o quast \
  -l MegaHit,Ray_31,velvet_31,velvet_51,idba_ud \
  megahit_out/final.contigs.fa \
  ray_31/Contigs.fasta \
  velvet_31/contigs.fa \
  velvet_51/contigs.fa \
  idba_ud_out/contig.fa

QUAST generates HTML reports including a number of interactive graphics. To access these reports, copy the
quast directory to your `public_html` folder::

  cp -r quast ~/public_html

After that, you can load the reports in your web browser::

  http://YOUR_AWS_IP/~ubuntu/quast/summary/report.html
  http://YOUR_AWS_IP/~ubuntu/quast/combined_quast_output/report.html


