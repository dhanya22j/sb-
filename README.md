import pandas as pd
from gtfparse import read_gtf

# Load the GTF file
gtf_file = "gencode.v47.annotation.gtf.gz"  # Replace with your GTF file path
gtf_data = read_gtf(gtf_file)

# Filter for entries where the feature type is 'gene'
gene_entries = gtf_data[gtf_data["feature"] == "gene"]

# Extract gene_id and gene_name columns
gene_info = gene_entries[["gene_id", "gene_name"]].drop_duplicates()

# Display the first few rows
print(gene_info.head())
