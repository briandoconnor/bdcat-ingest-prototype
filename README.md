# README

Repo for experimenting with data preparation and upload for the BDCat project.

## Setup

    conda create -n python_3_7_4_20200619 python=3.7.4
    conda create --name nimbus--data-ingest python=3.7.4
    conda activate nimbus--data-ingest
    pip install awscli
    pip install boto3

1. Create large file called big_binary.MOV in current directory (should be > 8 MB)

2. Run `aws configure`

3. For testing, update study\_id fields in sample.tsv. Then create aws s3 buckets with the name `<study_id>-<consent_code>`

## Running Code


    conda activate nimbus--data-ingest
    python process.py --aws --tsv sample.tsv 

manifest file will be located at sample.manifest.tsv

## TODO

* ensure md5sum code for AWS works for files < 5G too
* What additional metadata?  Beyond DRS metadata? -> U. Chicago help neede
* Checksum strategy 
* AWS and Google upload support -> currently have AWS via boto
* Setup process with Noble -> bucket creation SOP
* Handoff process with U. Chicago -> manifest handoff SOP
* High-performance uploads and parallelization testing
* Packaging of software to make it easier for Mac/Win users (optional?)

