## What is Firepony and what can I expect from it?

By Geraldine_VdAuwera

<h3>Firepony in a nutshell</h3>

<p>Firepony is a base quality score recalibrator for aligned read data sets. It recalculates the quality scores for each nucleotide in a SAM/BAM file based on the original quality data generated by the sequencer plus the empirical data obtained by running alignment.</p>

<p>The algorithm is a re-engineering of the base quality score recalibrator in the Genome Analysis Toolkit. It generates identical results, but runs much faster.</p>

<p><strong>Note that this tool was written by external collaborators of the GATK team and is their sole responsibility. To be clear, Firepony is not part of the official GATK software and is not tested/validated by the GATK developers. Use at your own risk.</strong></p>

<hr></hr><h3>How Firepony fits into your existing processing pipeline (workflow and command line usage)</h3>

<p>Firepony is meant to be a drop-in replacement for the BQSR step in GATK. The output of Firepony is a table that can be used as input for the PrintReads tool in GATK.</p>

<p>Existing pipelines can be modified by replacing the BQSR step (i.e., running GATK with the <code class="code codeInline" spellcheck="false">-T BaseRecalibrator</code> argument) with Firepony, as outlined in the accompanying documentation.</p>

<hr></hr><h3>Technical requirements and expected performance</h3>

<p>Firepony runs on Linux systems based on Intel CPUs with 64-bit support and at least 16GB of RAM. It can optionally make use of NVIDIA GPUs (Kepler class or higher with at least 4GB of memory) for higher performance.</p>

<p>Compared to GATK, Firepony runs anywhere from 5x to 12x faster, depending on the specific hardware and data set used. The output of Firepony is compatible with GATK, meaning it can be used by subsequent processing steps that rely on GATK.</p>
