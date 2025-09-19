Linux Fundamentals/My Notes.md

🐧 Linux Fundamentals Cheat Sheet
🔹 Command Basics

Format: command -options arguments

Case-sensitive: LS ≠ ls

Navigation & Files

pwd → Print working directory (where am I?)

ls → List files

ls -a → Show hidden files (. prefix)

ls -l → Show details (permissions, timestamp, size)

cd dirname → Change directory

mkdir dirname → Make directory

mkdir -p project/src/components → Nested dirs

rmdir dirname → Remove empty directory

rm file → Remove file

rm -r dir → Remove directory recursively

⚠️ rm -rf / → DANGEROUS, deletes everything

touch file.txt → Create empty file

cp file1 file2 → Copy file

cp -r dir dir_copy → Copy directory

mv file1 file2 → Rename/move file

🔹 Viewing & Editing Files

echo "text" → Print string

echo "text" > file.txt → Write (overwrite) file

echo "text" >> file.txt → Append to file

cat file.txt → Show contents

cat f1 f2 > combined.txt → Concatenate

head file.txt → First 10 lines

head -n 5 file.txt → First 5 lines

tail file.txt → Last 10 lines

tail -n 3 file.txt → Last 3 lines

grep "word" file.txt → Search in file

VIM Editor

Modes: insert (i), command (esc), visual

Save & quit: :wq!

Quit no save: :q!

Delete line: dd

Undo: u, Redo: Ctrl+r

Search: /word then n/N

🔹 Permissions

ls -l → Show permissions

rwx rwx rwx → user | group | others

Change permissions:

chmod u+x file → Add exec to user

chmod 750 file → (7=RWX, 5=R-X, 0=---)

Change owner:

sudo chown user file

sudo chgrp group file

sudo chown -R user:group dir

🔹 Users & Groups

whoami → Current user

sudo → Run command as root

sudo su → Switch to root shell

Create user:

sudo useradd newuser

sudo passwd newuser

su - newuser (switch)

Add to sudo group:

sudo usermod -aG sudo newuser

Groups:

cat /etc/group → Show groups

sudo groupadd devops → Create group

sudo usermod -aG devops newuser → Add user to group

sudo gpasswd -d user group → Remove from group

🔹 Shells & Customisation

echo $SHELL → Show current shell

cat /etc/shells → List available shells

Change shell:

chsh -s /bin/zsh

sudo chsh -s $(which zsh) $(whoami)

Customise Zsh:

Install Oh My Zsh

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"


Powerlevel10k theme:

git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/.oh-my-zsh/custom/themes/powerlevel10k


Edit config: vim ~/.zshrc

🔹 Standard Streams

STDIN (0), STDOUT (1), STDERR (2)

Redirect:

command > file → Output

command 2> error.log → Errors

command &> all.log → Output + Errors

🔹 Environment Variables

printenv → Show all variables

echo $HOME → Reference variable

export MY_VAR="test" → Create variable

echo $PATH → Show PATH

🔹 Aliases

alias hi='echo "hello world"'

Add permanent alias in ~/.zshrc

🔹 Useful Shortcuts

Tab → Auto-complete file/dir names

Ctrl+R → Search command history

history → Show history

!n → Run history command n

sudo !! → Run last command with sudo
Create The Shell.md
