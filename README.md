# Some notes to work in bash and useful functions

I started my PhD with no knowledge of bioinformatics. However, I learnt some very basic but useful functions that made my life way easier. This repository aims to share some of those functions used in Bash to work in microbial metagenomics.

<i><b>Function 1</i></b>:
````
rename  's/-/_/' *.fna 
````
I used this function to edit the name of all the .fna files, changing all dashes (-) for underscores (_). Really useful function to homogenize our file names.

<i><b>Function 2</i></b>:

````
for file in *.fa.protein.translations.faa ; do
    mv "$file" "${file/.fa.protein.translations/}"
done
````

With this simple loop we eliminate from the names of all the .faa files one section of the name (<i>.fa.protein.translations</i>), making the names of the files more simple and shorter.

On a similar mode, we can add text also:
````
for file in * ; do 
    mv -- "$file" "OUT_$file" ; 
done
````
Here we add "<i>OUT_</i>" to all the files in the folder.

<i><b>Function 3</i></b>:

````
ls *.fna > list_files.txt
````

Here we create a list of all the .fna files on a folder.

<i><b>Function 4</i></b>:

````
sed -i 's:"::g' my_file.tsv
````

This function eliminates all the " within the file named <i>my_file.tsv</i>.
