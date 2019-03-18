+++
title = "Bash/Shell Basics"
date = 2019-02-26T13:03:26-05:00
weight = 2
enableEmoji = true
+++
{{% notice info %}} This page is a collection of resources and notes we've taken over the years.
{{% /notice%}}
![Forgetful](/savior/bash/forget.gif?classes=shadow)

### Check if direction is empty
```bash
if [ -z "$(ls -A /path/to/dir)" ]; then
   echo "Empty"
else
   echo "Not Empty"
fi
```
### change spaces in filename to _
```bash
for file in *; do mv "$file" `echo $file | tr ' ' '_'` ; done 
```
### change spaces in filename to _ with awk
```bash
mv "$file" `echo $file | awk '{gsub(/>>/,"_")} 1'`
```
### i can't remember exactly what this was for but i was renaming files and trying to get rid of extra text at the end of the name (hence the rev(ersing) to and from)
```bash
base_orig=`echo $j | cut -d "." -f1`; base_new=`echo $j | cut -d "." -f1 | rev | cut --complement -d "_" -f2 | rev | cut -d "_" -f 4-`; echo $base_spc $base_orig $base_new;
```
### find scanning info in json file
```bash
for i in `ls ./P*/dwi/*.nii.gz | cut -d . -f1`; do if [[ `cat ${i}.json | grep "SeriesDescription" | grep -o "_FA"` == "_FA" ]] || [[ `cat ${i}.json | grep "SeriesDescription" | grep -o "_ColFA"` == "_ColFA" ]] || [[ `cat ${i}.json | grep "SeriesDescription" | grep -o "_EXP"` == "_EXP" ]]; then echo $i; fi; done
```

### set an alias for a command, can go in .bash_profile or .bashrc
```bash
alias ls=l #for example
```
### set up config file to make aliases for remote login
in ~/.ssh/config (a text file) contains, for example:
```bash
Host typenameofserver
User typeyourusername
HostName typecompletehostname #e.g. graham.computecanada.ca
```
so that now i can type ssh graham and it will know to ssh to username@graham.computecanada.ca