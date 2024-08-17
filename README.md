
# Gene Data Retrieval and Integration with NCBI Entrez API

This Jupyter notebook automates the retrieval of gene information from the NCBI Entrez Gene database using a list of gene IDs, processes the XML data, and integrates it with existing gene data stored in an Excel file. The fetched information is then merged with the Excel data, producing an updated version for further analysis or use.

## Features

- **NCBI Entrez Gene API Integration**: Retrieve up-to-date gene data such as gene name, status, description, and summary using a list of gene IDs.
- **Error Handling with Retry Mechanism**: Handles network and API errors by implementing exponential backoff and retries.
- **Excel Data Integration**: Merges the fetched gene data with an existing Excel dataset.
- **Efficient XML Parsing**: Extracts relevant information from the returned XML data in a structured manner.

## Prerequisites

- Python 3.x
- Required libraries: `pandas`, `tqdm`, `xml.etree.ElementTree`, `Bio` (from Biopython for Entrez API), `openpyxl` (for handling Excel files)

Install the dependencies by running:

```bash
pip install pandas tqdm biopython openpyxl
```

## Excel File Structure

Before running the notebook, ensure that the Excel file you're using is structured with the following columns:

| GeneID   | Other_Column1 | Other_Column2 | ... |
|----------|---------------|---------------|-----|
| 1234     | Value1        | Value2        | ... |
| 5678     | Value3        | Value4        | ... |

The important column is `GeneID`, which should contain the numerical gene IDs that will be used to query the NCBI Entrez Gene database. Other columns can contain any additional data relevant to your analysis.

### Output Excel File

The updated Excel file will include the original data along with the new columns from the NCBI query, such as:

| GeneID   | Gene Name  | Status    | Description             | Summary                     |
|----------|------------|-----------|-------------------------|-----------------------------|
| 1234     | GeneName1  | Active    | Gene description here... | Summary of gene function... |
| 5678     | GeneName2  | Discontinued | Description...          | Summary...                  |

## How to Run

1. Provide a list of gene IDs (either manually or by reading from an Excel file).
2. Execute the notebook, which will fetch data from the NCBI Entrez Gene API.
3. The results will be merged with your existing Excel data and saved as `updated_osman.xlsx`.

## License

This project is licensed under the MIT License:

```
MIT License

Copyright (c) 2024 Felix Meier

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
