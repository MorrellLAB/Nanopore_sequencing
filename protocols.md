# RAPID kit
Please see the record in my [note book](https://github.com/lilei1/Nanopore_sequencing/blob/master/Notes_pic/nanopore_notes.pdf).

This kit usually can get 2.3-2.9 Gbases data for barley samples (I tested wild barley and elite barley).

**Warning**!! Please turn off the basecall during sequencing, otherwise, it will make the living base call very slow.

After the finish loading sample, remember to type "caffeinate", which will keep you compute aweak and make sure the sequencing will run smoothly.

FFPE DNA repair is not usefull to improve the data volumn for RAPID kit.

Sometimes the miKnow GUI will look werid, you can press "command+R" to refresh the GUI.

After the sequencing finishe the full run (48 hours), you can run GUPPY to do base call

Here is the command line I used:

```
/Users/LiLei/softwares/ont-guppy-cpu/bin/guppy_basecaller --input_path /Nanopore_data/Morex_sample2_20190415/Morex_sample2_20190415/20190415_2134_MN28971_FAK17129_965ac103/fast5 --save_path /Nanopore_data/basecall --flowcell FLO-MIN106 --kit SQK-RAD004

/Users/LiLei/softwares/ont-guppy-cpu/bin/guppy_basecaller --input_path /Nanopore_data/WBDC355-run2/WBDC355-run2-20190419/20190419_2033_MN28971_FAK25774_d948a82a/fast5 --save_path /Nanopore_data/basecall/WBDC355 --flowcell FLO-MIN106   --kit SQK-RAD004
```
After the basecall, you can backup the data in S3 or in hard drive.

You can also use [GLOBUS](https://app.globus.org/file-manager?destination_id=fb6f1c6b-86b1-11e8-9571-0a6d4e044368&destination_path=%2F~%2FScratch%2F&origin_id=d865fc6a-2db3-11e6-8070-22000b1701d1&origin_path=%2F~%2F) to backup the data to your S3.

Here is the commandline I used for back up data to external hard drive
```
rdiff-backup --force /Library/MinKNOW/data/reads  /Volumes/Drive8/FAJ07225_FAH86411/reads 
```

---

# Ligation kit (Morex-sample2)
I started the size selected DNA with fragment length >40kb, 500ng.

I skipped the FFPE DNA repairing step, and started from the Adapter ligation and clean-up, but I did not get any data.

The report picture from miKNOW looks werid, and the enhance support suggested that we should start with the FFPE step, and load more DNA.






