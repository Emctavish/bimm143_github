# bimm143_github
My classwork for [BIMM 143](https://bioboot.github.io/bimm143_W26/schedule/#14) at UC San Diego.

cd: Change Directory
mkdir: Make a new directory
rm: Delete files and directories
nano: A very basic text editor that is always available
less: To view/read text files page by page (pager program)


My AWS instance:
ssh -i ~/Downloads/bimm143_erin.pem ubuntu@ec2-35-87-77-169.us-west-2.compute.amazonaws.com

To copy from my AWS instance
scp -i ~/Downloads/bimm143_erin.pem ubuntu@ec2-35-87-77-169.us-west-2.compute.amazonaws.com:~/work/results.tsv .


Q. What does the star character accomplish here? Ask Barry, or your class neighbor, if you are not sure!

Unzips all the files at once.

Q. How many sequences are in this mouse.1.protein.faa file? Hint: Try using grep to figure this out…

55052

Q. What happens if you run the above command without the > mm-first.fa part?

The output is not saved in the file and instead directly in the terminal.

Q. What happens if you were to use two ‘>’ symbols (i.e. >> mm-first.fa)?

Adds it onto existing content.

Q.How would you determine how many sequences are in the mm-second.fa file?
grep -c ">" mm-second.fa   96

## Unix command review homework questions

>Q1. List the UNIX bash shell commands to:

• open a secure shell on a remote machine:
	ssh erin@remote_host

• make a new folder in your home area called "test":
	mkdir ~/test	

• download this file "https://files.rcsb.org/download/5P21.pdb.gz":
	wget https://files.rcsb.org/download/5P21.pdb.gz	

• unzip/decompress it the file:
		gunzip 5P21.pdb.gz

• print to screen the first 6 lines:
		head -n 6 5P21.pdb

• print to lines beginning with ATOM to a new file called "coords.pdb":
  grep "^ATOM" 5P21.pdb > coords.pdb
  
  
>Q2. List the UNIX commands to copy securely the file "myaln.fa" in your current
working directory to your home area on the remote machine "biglabcluster.ucsd.edu":

scp myaln.fa erin@biglabcluster.ucsd.edu:~


>Q3. The alignment file “myaln.fa” is not in your current working directory but it is in your
“Downloads” directory. Write the R code to import this alignment to the named object “aln”
using a function from the bio3d package. 

library(bio3d)

aln <- read.fasta("~/Downloads/myaln.fa")
