🎮 OverTheWire Bandit Notes

🔑 Login

ssh bandit0@bandit.labs.overthewire.org -p 2220


Password will change for each level.

Level 0 → 1

Command:

cat readme


Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

Level 1 → 2

File named - (dash). Need ./- to read.

cat ./-


Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

Level 2 → 3

File has spaces in name → wrap in quotes or escape spaces.

cat "./filename with spaces"
# OR
cat ./filename\ with\ spaces


Password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

Level 3 → 4

Hidden file inside directory. Use:

ls -a
cat .hidden


Password: pIwrPrtPN36QITSp3EQaw936yaFoFgAB

Level 4 → 5

ELF file is binary → only ASCII/unicode readable file is correct.

file ./*


Password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh

Level 5 → 6

Search for file by size + non-executable + ASCII.

find . -type f -size 1033c ! -executable -exec file {} \; | grep ASCII
cat ./filename


Password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

Level 6 → 7

File owned by specific user & group. Redirect errors away.

find / -type f -user bandit7 -group bandit6 2>/dev/null
cat /path/to/file


Password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

Level 7 → 8

Search text in a file:

grep "millionth" data.txt


Password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

Level 8 → 9

Find the only unique line:

sort data.txt | uniq -u


Password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

Level 9 → 10

Find human-readable strings inside binary:

strings data.txt | grep "=="


Password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

Level 10 → 11

Decode Base64 text:

base64 -d data.txt


Password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

Level 11 → 12

ROT13 substitution cipher:

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'


Password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
