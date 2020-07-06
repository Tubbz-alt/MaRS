# Instructions to upload MaRS data to the NCBI SRA (Sequence Read Archive) via Aspera transfer

## Follow the basic steps as outlined in the [SRA Submission Quick Start](https://www.ncbi.nlm.nih.gov/sra/docs/submit/)
1. Sign in to your NCBI account.
2. Register your biological samples at the [BioSample database](https://www.ncbi.nlm.nih.gov/biosample/) under the MaRS BioProject [PRJNA428490](https://www.ncbi.nlm.nih.gov/bioproject/?term=PRJNA428490). 
3. Create a new SRA data submission and submit your SRA metadata file.
4. Follow the prompts on the screen to upload your files, selecting the Aspera option.
5. Upload sequence files using Aspera Connect via command line (see below) or [SRA fle upload options](https://www.ncbi.nlm.nih.gov/sra/docs/submitfiles/)
* Note: Do not use FTP transfer. This option times out too often/has too many connection issues with our experience.

## File transfer using Aspera command line after submitting SRA metadata file
1. Download and install Aspera command line, if you do not currently have this installed.
    * Download **aspera cli** from [this link](http://downloads.asperasoft.com) under "Client Software"
    * Run the downloaded shell script
    * In the command line run the export PATH command printed on your screen from output from the shell script
      * (You also can add this path to your ~/.bash_profile for future use).
2. Download the aspera key from the link provided in the SRA submission portal prompting you to upload your files
3. Make sure all of your sequence files are grouped together in the same directory with no other files
4. Run the following command in the command line
    * ascp -i <path/to/key\_file> -QT -m 1100 -k 1 -d <path/to/folder\_with\_files(s)> subasp\@upload.ncbi.nlm.nih.gov\:\<destination directory as provided on the SRA submission screen>
5. Files are now uploaded
6. Select the pre-loaded folder and click submit.
