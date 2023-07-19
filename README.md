# Final Project in Deep Learning Course at Ben Gurion University

Stav Dratva & Peleg Eliyahou (Group 3)

This repository contains code to reproduce the results of Enhancing Question Classification with Augmented Data project.

### Installing Requirements

In order to run the code, you should make sure the libraries requirements are satisfied.
Install the requirements using pip

```bash
pip install -r requirements.txt
```


## Running the Experiments

To run the experiments, you can use the following command:

```bash
python main.py TREC BERT --learning_rate=5e-5 --batch_size=128 --num_train_epochs=10 > output.txt
```


### Data Augmentation 

To run the code to produce the data augmentation files, you should run the following Python files from the "data_augmentation" directory:


1. augment.py - The code that produces the EDA augmented files. You should change the following parameters in the "arguments" dictionary:
   num_aug = The number of augmented sentences that will produce from each original record.
   output_clean, output, output_labels = The file path of the output files.
2. backtranslation.py - The code that performs back translation to Hebrew from the original dataset.
   The chosen target language for this experiment was Hebrew. If you want toperformm back translation to another language you can change the value of "target_lang" in the "arguments" dictionary.
   The available languages are as follows:
   af - afrikaans
sq - albanian
am - amharic
ar - arabic
hy - armenian
az - azerbaijani
eu - basque
be - belarusian
bn - bengali
bs - bosnian
bg - bulgarian
ca - catalan
ceb - cebuano
ny - chichewa
zh-cn - chinese (simplified)
zh-tw - chinese (traditional)
co - corsican
hr - croatian
cs - czech
da - danish
nl - dutch
en - english
eo - esperanto
et - estonian
tl - filipino
fi - finnish
fr - french
fy - frisian
gl - galician
ka - georgian
de - german
el - greek
gu - gujarati
ht - haitian creole
ha - hausa
haw - hawaiian
iw - hebrew
he - hebrew
hi - hindi
hmn - hmong
hu - hungarian
is - icelandic
ig - igbo
id - indonesian
ga - irish
it - italian
ja - japanese
jw - javanese
kn - kannada
kk - kazakh
km - khmer
ko - korean
ku - kurdish (kurmanji)
ky - kyrgyz
lo - lao
la - latin
lv - latvian
lt - lithuanian
lb - luxembourgish
mk - macedonian
mg - malagasy
ms - malay
ml - malayalam
mt - maltese
mi - maori
mr - marathi
mn - mongolian
my - myanmar (burmese)
ne - nepali
no - norwegian
or - odia
ps - pashto
fa - persian
pl - polish
pt - portuguese
pa - punjabi
ro - romanian
ru - russian
sm - samoan
gd - scots gaelic
sr - serbian
st - sesotho
sn - shona
sd - sindhi
si - sinhala
sk - slovak
sl - slovenian
so - somali
es - spanish
su - sundanese
sw - swahili
sv - swedish
tg - tajik
ta - tamil
te - telugu
th - thai
tr - turkish
uk - ukrainian
ur - urdu
ug - uyghur
uz - uzbek
vi - vietnamese
cy - welsh
xh - xhosa
yi - yiddish
yo - yoruba
zu - zulu

Process finished with exit code 0

Process finished with exit code 0

    

To run the experiments on the MR dataset using the ALBERT model and our parameters, you can use the following command:

```bash
python main.py MR ALBERT --learning_rate=1e-5 --batch_size=32 --num_train_epochs=10 --dropout=0
```

### Scripts
There are also scripts to run the experiments on all datasets with our selected parameters.
These scripts can be found in the [run_scripts](run_scripts) folder.

For further information on the scripts, see the [README](run_scripts/README.md) in the run_scripts folder.

## Structure of the repository
The repository is structured as follows:

    .
    ├── data                    # Data files
    ├── run_script              # Bash scripts to run all experiments
    ├── convert2dadgnn.py       # Script to convert data to DADGNN format
    ├── convert2inductTGCN.py   # Script to convert data to InductTGCN format
    ├── convert2SHINE.py        # Script to convert data to SHINE format
    ├── data.py                 # Data loading and representation
    ├── ensemble_models.py      # Ensemble models declaration
    ├── models.py               # MLP and LSTM declaration
    ├── main.py                 # Main script to run the experiments
    └── requirements.txt        # Requirements file

The source code of the foreign models is not included in this repository.
You can find the source code of the foreign models in the following repositories:

- [InductTGCN](https://github.com/usydnlp/InductTGCN)
- [SHINE](https://github.com/tata1661/SHINE-EMNLP21)
- DADGNN: Not publicly available

## License

This project is licensed under the [MIT](LICENSE) License - see the [LICENSE](LICENSE) file for details


## Acknowledgments

We would like to thank the authors of the following repositories for making their code publicly available:
- The WideMLP code was adopted from [Lukas Galke](https://github.com/lgalke/text-clf-baselines)
