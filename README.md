# Winnipeg-Sales-Book-to-CSV
Convert Winnipeg's Sales Book PDFs to CSV


The City of Winnipeg provides real estate transaction data for the city in the form of a Sales Book.

[City of Winnipeg Sales Book Page] (http://winnipegassessment.com/AsmtTax/English/SelfService/SalesBooks.stm)

This data is provided as tables within PDF documents. To make this data more accessible, it is necessary to convert it into a machine-readable format like CSV.

## Requirements:

1. Pandas

  `conda install pandas`

2. Camelot

  `conda install -c conda-forge camelot-py`

## Usage:

1. Collect the PDF data files with:

  `bash collect_urls.sh > file_list.txt`

  `wget -i file_list.txt`

This downloads the files to your current directory.

2. Read the files in and convert to PDF, then clean them up.

  `python3 convert_pdfs.py pdf_dir/ csv_dir/`

  `python3 clean_pdf_data.py csv_dir/ clean_dir/ 4 \
      'idx,address,roll_no,sale_yr,sale_mth,sale_price,adj_sale_price'`
