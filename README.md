# Github repository dataset
Scraping more than 1M repositories from GitHub!

## The 1M dataset

The dataset (TXT format) is located here:

https://github.com/philipperemy/Github-full-data-set/blob/master/data_1m/GITHUB.1M.txt

The fields recorded are:
- name
- clone_url
- created_at
- forks (FORKS)
- has_issues
- language (COMPUTER LANGUAGE)
- subscribers_count (WATCH)
- watchers_count (STARTS)
- stargazers_count
- size

Due to size limitations, I had to narrow down the available tags to those above. I provide all the tags for the 100k dataset. More information below.

## What if I want to scrape my own data?

### Let's get started!
```
git clone https://github.com/philipperemy/Github-full-data-set.git
cd Github-full-data-set/
sudo pip3 install -r requirements.txt
```

### Read from pre existing data (100k dataset)
```
cat data_100k/x* > data_100k/GITHUB.tar.gz # because GitHub does not allow files bigger than 100Mb.
md5sum data_100k/GITHUB.tar.gz # 5886b24033991283a4dbfa6b328be011  data_100k/GITHUB.tar.gz
tar xvzf data_100k/GITHUB.tar.gz # goes to GITHUB/
python3 read.py GITHUB/
```

### Generate your own data
```
python3 main_run_scraper.py <GITHUB_USERNAME> <GITHUB_PASSWORD> GITHUB/
```

### Example of data from the 100k dataset
```
OUTPUT_DIR = GITHUB/
Search files here: GITHUB/**.pkl
--------------------------------------------------------------------------------
ID         =  0
URL        =  https://github.com/10gen/external
NAME       =  external
WATCH      =  3
STARTS     =  2
LANGUAGE   =  JavaScript
FORK       =  1
--------------------------------------------------------------------------------
ID         =  1
URL        =  https://github.com/4l3x2k/8086macs
NAME       =  8086macs
WATCH      =  2
STARTS     =  0
LANGUAGE   =  C
FORK       =  0
--------------------------------------------------------------------------------
ID         =  2
URL        =  https://github.com/A1kmm/cellml_meta_1_1
NAME       =  cellml_meta_1_1
WATCH      =  2
STARTS     =  3
LANGUAGE   =  None
FORK       =  0
--------------------------------------------------------------------------------
ID         =  3
URL        =  https://github.com/aaronchi/jrails
NAME       =  jrails
WATCH      =  3
STARTS     =  721
LANGUAGE   =  Ruby
FORK       =  82
```

NB: When you scrape yourself, there are way more tags than just those represented above.
Please refer to the links below for a complete documentation of all the available tags.
- https://github.com/PyGithub/PyGithub
- https://github.com/PyGithub/PyGithub/blob/master/github/tests/Repository.py 
