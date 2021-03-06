#  Commands & Shortcuts

- [Linux Directory](#linux-directory)
- [Linux Files](#linux-files)
- [Linux System](#linux-system)
- [URL](#url)
- [SSH](#ssh)
- [Tmux](#tmux)
- [VIM](#vim)
- [Gnuplot](#gnuplot)
- [GitHub](#github)
- [Python](#python)
- [PIP](#pip)
- [Virtualenv](#virtualenv)
- [Venv](#venv)
- [Flask](#flask)
- [Django](#django)
- [Elasticsearch](#elasticsearch)
- [Vagrant](#vagrant)
- [Docker](#docker)
- [Redis & RQ](#redis-&-rq)
- [Hadoop](#hadoop)

##  Linux Directory

new window in the terminal:

    Ctrl + Shift + T

close current window in the terminal:

    Ctrl + Shift + W

change window in the terminal:

    Shift + Left/Right

print working directoty:

    pwd

list directory content:

    ls

detailed list directory content:

    ls -la

detailed list directory content by size:

    ls --sort=size -l

detailed list directory content sorted by changing time:

    ls --sort=time -l

example of similarity:

    ls --all --human-readable -l
        == ls -a -h -l
        == ls -ahl
        == ls -lah

create new directory:

    mkdir /dir

create new directory and her 'parents':

    mkdir -p /dir

create multiple directoties:

    mkdir ./{dir1,dir2,dir3}

create new file:

    touch /dir/file

create multiple files:

    touch name1 name2

create multiple files with same char/extensions:

    touch n{ame1,ame2}.py

enter directory:

    cd /dir

delete file:

    rm /dir

delete directory:

    rm -r /dir

delete directory without questions:

    rm -rf /dir

copy file from dir to the new dir:

    cp /dir/file /new_dir

copy dir to the new dir:

    cp /dir /new_dir

move file/directory:

    mv /dir or /dir/file /new_dir

rename file:

    mv filename new_filename

run program:

    program_name

run program in background mode instantly:

    program_name &

stop program execution:

    Ctrl + C

suspend program execution:

    Ctrl + Z

continue program execution:

    fg

continue program execution in the backgound mode:

    bg

list of running programs:

    jobs

continue program execution with specified number:

    fg %<num>

continue program execution in the backgound mode w sn:

    bg %<num>

##  Linux Files

view file content:

    cat /file

view file content in new window:

    less /file

edit file content:

    nano /file

save stdout of file into another file:

    /file.py > /file_output.txt

who using this system right now:

    users

user groups:

    groups user

permissons legend:

    drw-rw-r--
    -rw-rw-r--
    1  2  3   (d = dir, - = file) (1 - owner, 2 - group, 3 - other)

change file permissions:

    chmod [ugoa][+-][rwx] dir (u - user, g - group, o - oher, a - all)
        ex: chmod ug+rw file.txt

make file executable:

    chmod +x filename

input from file to program:

    program < file

output from program to file:

    program > file

output from program to file with full output:

    program >> file

output program errors to file:

    program 2> file

output program errors to file with full output:

    program 2>> file

program pipe:

    program1 | program 2 | program 3

download files:

    wget url

download file and save in specified directory:

    wget -P /dir url

download file and save with specified name:

    wget -O /dir/filename url

continue downloading if interrapted:

    wget -c url

check url for availability:

    wget --spider

download files with urls from txt file:

    wget -i /file.txt

recursive downloading from url:

    wget -r -l deep

find file in current directory:

    find -name 'file'

find file in specified directory:

    find /dir -name 'file'

find file in directory with specified parameters:

    find -name '*.py'

find file without register parameters:

    find -iname file

find file with specified path:

    find -path path (ex: find -path "*subdir*/*jpg")

find files with specified size:

    find -size size

find files in less then specified dir depth:

    find -maxdepth num

find files in more then specified dir depth:

    find -mindepth num

find string in file:

    grep 'str' file

count the number of string entries:

    grep -c 'str' file

find string in all files in specified directory:

    grep  -r 'str' file

list of files with specified string:

    grep -l 'string' file

list of files without specified string:

    grep -L 'string' file

find the number of line with specified string:

    grep -n 'string' file

find limited number of line with specified string:

    grep -m num 'string' file

find line with specified string and limited lines after:

    grep -A num 'string' file

find line with specified string and limited lines before:

    grep -B num 'string' file

find line with specified string and limited lines around:

    grep -C num 'string' file

find pattern with regexp:

    grep -E "regexp"  file

operate with file:

    sed 'instruction' file

change specified word by another and save to another file:

    sed 's/name1/name2/g' file > new_file

output specified lines from file:

    sed -n 'num1,num2p' file

output all lines except specified lines from file:

    sed 'num1,num2d' file

output specified quantity of lines from start:

    head -n num file

output specified quantity of lines from end:

    tail -n num file | less

count lines in file:

    wc -l file

count words in file:

    wc -w file

count charcters in file:

    wc -c file

compare two files:

    diff -qr dir1/ dir2/

compare two files and open result in new window:

    diff file1 file2 | less

create .zip archive:

    zip archive.zip file file1 file2..

create .tar archive:

    tar -cvf archive.tar file file1 ...

create .gz archive:

    gzip file

create .gz archive from .tar archive:

    gzip archive.tar

unpack .zip archive:

    unzip archive.zip

unpack .gz archive:

    gunzip archive.gz

unpack .tar archive:

    tar -xvf archive.tar

unpack .tar.gz archive:

    tar -xzvf archive.tar.gz

##        Linux System

stop program execution:

    Ctrl + C

pause program execution:

    Ctrl + Z

continue program execution:

    fg

continue program execution in the backgound mode:

    bg

list of running programs:

    jobs

continue program execution with specified number:

    fg %num

continue program execution in the backgound mode w sn:

    bg %num

view your processes:

    ps

view processes in real time:

    top

view processes specified user:

    top -u name

try to eliminate processes with specified number:

    kill num

finally eliminate processes with specified number:

    kill -9 num

information about RAM:

    free

information about CPU core quantity:

    nproc

information about CPU:

    lscpu

run program in few threads (p = quantity of threads):

    program -x -p num

how much space using specified dir:

    du -h dir

how much space using current dir with specifed depth:

    du --max-depth 1 -h

system storage info(used/available):

    df -h

##        URL

take information about URL:

    curl -v 'url'

##        SSH

create new ssh keys:

    ssh-keygen

start ssh-agent in the background:

    eval `ssh-agent -s`

add  private ssh key to the ssh-agent:

    ssh-add ~/.ssh/id_rsa

view your public keys:

    ssh add -L

view ssh fingerprints:

    ssh add -l

delete ssh identities from ssh agent:

    ssh-add -D

check that the key is being used by trying to connect to host:

    ssh -vT host

entrance to server:

    ssh login@addres -port

1 STEP. create a key:

    ssh-keygen

2 STEP. add key to the agent:

    ssh-add

view public key:

    cat ~/ssh/id_rsa.pub

edditing autorised keys on server:

    nano ~/.ssh/autorised_keys

3 STEP enter to the server:

    ssh login@addres -port

4 STEP add public key to remote server:

    ssh-copy-id -i ~/ssh/id_rsa.pub adress

exit from server:

    exit

copy files from server (dir1) to client (dir2):

    scp -P port login@adress:dir1 dir2

copy full dir from server (dir1) to client current dir:

    scp -r login@adress:dir1 .

copy files from client (dir1/file) to server (dir2):

    scp -P port dir1/file login@adress:dir2

##        Tmux

create new windiow:

    Ctrl + B C

give a name to the window:

    Ctrl + B ,

change to specified window:

    Ctrl + B num

change to next/prev window:

    Ctrl + B N/P

close window:

    Ctrl + B X

temporary out from tmux:

    Ctrl + B D

back to work with tmux:

    tmux a

view list of running tmux's:

    tmux list-sessions

kill sessions:

    tmux kill-session

history view mode:

    Ctrl + B PgUp

close history view mode:

    Ctrl + C

split window horizontaly:

    Ctrl + B "

split window vertically:

    Ctrl + B %

swap panes:

    Ctrl + B o

show pane numbers:

    Ctrl + B q

display big clock:

    Ctrl + B t

##        VIM

in build vim lessons:

    vimtutor

delete charchter under the cursor:

    x

delete a word:

    dw

delete to the end of a line:

    d$

delete all line from cursor:

    dG

copy:

    y

copy word:

    yw

copy 'num' words:

    y'num'w

copy line:

    yy

copy 'num' lines:

    y'num'

paste above cursor:

    P

paste below cursor:

    p

replace the character under cursor with x:

    rx

replace the characters under cursor until in replace mode:

    R

find characters:

    /chars or ?chars and move with n or N

substitute the first occurrence of 'new' for 'old':

    :s/old/new

substitute globally in the line, change all occurrences of "old" in the line:

    :s/old/new/g

change all occurrences of "old" between lines #1 and #2:

    :#1,#2s/old/new/g

change every occurrence in the whole file:

    :%s/old/new/g

to find every occurrence in the whole file, with a prompt whether to substitute or not:

    :%s/old/new/gc

excecute an external command:

    :!command

insert content of a file:

    :r filename

insert content of a command:

    :r !command

list of possible completions for command:

    :command  Ctrl+D

undo last command:

    u or :u

undo all changes since opening buffer:

    :u1|u

##        Gnuplot

make chart by file (1 = x, 2 = y):

    plot file using 1:2

make few charts by file:

    plot file using 1:2, file using 1:3

add names for coordinates:

    plot file using 1:2 title 'name'

add names for coordinates automatically from first line:

    set key autotitle columnhead

set autoscale:

    set autoscale xy / unset autoscale xy

##        GitHub

create repository on github.com and clone to the location where you want:

    git clone https://github.com/my_username/my_new_repository

stage the file for commit to my local repository:

    git add file / git add .

to unstage a file:

    git reset HEAD file / git reset file

commit the file that you've staged in local repository:

    git commit -m "message"

to remove this commit:

    git reset --soft HEAD~1

push the changes to github:

    git push

initialize and add existing repository:

    git init

stage the file for commit to my local repository:

    git add .

commit the file that you've staged in local repository:

    git commit -m "message"

add URL for the remote repository:

    git remote add origin https://github.com/my_username/my_repository

verify the new remote URL:

    git remote -v

push changes to github:

    git push --set-upstream origin master

push changes to github with force:

    git push -f [alias] [branch]

if fatal: refusing to merge unrelated histories:

    git pull origin master --allow-unrelated-histories

check what is different from our last commit:

    git diff HEAD

check what is different in staged files  from last commit:

    git diff --staged

reset the file to the latest commited version:

    git checkout --file

pull down any new changes:

    git pull / git pull origin master

create new branch and switch to it:

    git checkout -b new_branch

merge the specifed branch's history into current one:

    git merge branch

delete file from repo:

    git rm --cached file

delete file from repo and from the local file system:

    git rm file

##        Python

check version:

    python -V / python3 --version

##        PIP

pip commands and options:

    pip

list of installed packages:

    pip list

list of outdated packages:

    pip list -o

check for broken packages:

    pip check

search in pip repository:

    pip search query

output installed packages in requirements format and save to file:

    pip freeze > requirements.txt

install packages from requirements.txt:

    pip install -r requirements.txt

unistall packages:

    pip unistall -r requirements.txt

##        Virtualenv

create new virtual enviroment with default python version:

    virtualenv name

create new virtual enviroment:

    virtualenv

specifed python version in virtual enviroment:

    vitrualenv -p python3 . or virtualenv -p /usr/local/bin/python3

activate virtual enviroment:

    source bin/activate

deactivate virtual enviroment:

    deacivate

check for instaled pacakges in current virtual enviroment:

    pip freeze

##        Venv


create new venv with python3:

    python3 -m venv project_name

activate venv:

    source project_name/bin/activate

##        Flask

seting flask app enviroment variable:

    export FLASK_APP=app_name.py

start flask app:

    flask run

start flask shell:

    flask shell

initialize flask database:

    flask db init

flask database migration with commentary:

    flask db migrate -m "comment"

apply migrations to the database:

    flask db upgrade

undoes the last migration:

    flask db downgrade

##        Django

run python with specified enviroment variable:

    python manage.py shell

START PROJECT <br />

create django project:

    django-admin startproject project_name

run django project:

    python manage.py runserver

run django project on specifed server:

    python manage.py runserver 0.0.0.0:8000

create app inside django project:

    python manage.py startapp app_name

DATABASE <br />

synchronie the database state with the current set of models and migrations:

    python manage.py migrate

tell django about some changes to your models:

    python manage.py makemigrations app_name

migration in sql:

    python manage.py sqlmigrate app_name 0001

check for any problem in your project without making migrations or toching db:

    python manage.py check

ADMIN <br />

create a user:

    python manage.py createsuperuser

##        Elasticsearch

run elasticsearch:

    ./bin/elasticsearch

run elasticsearch as a demon:

    ./bin/elasticsearch -d -p pid

##        Vagrant

create server:

    vagrant up

##        Docker

docker info:

    docker version

run docker deamon:

    sudo dockerd

build a container image and set the name and tag:

    docker build -t microblog:latest .

obtain a list of the images that you have locally:

    docker images

delete docker images:

    docker rmi 'imageid'

list of running containers:

    docker ps

stop the docker container:

    docker stop 'containerid'

##        Redis & RQ

start redis:

    redis-server

start worker:

    rq worker 'queue name'

##        Hadoop

copy small files:

    hdfs dfs -cp /dir/file1 /dir2/file2

copy big files:

    hdfs distcp /dir/file1 /dir2/file2

move files:

    hdfs dfs -mv /dir/file1 /dir2

copy from local system to hdfs:

    hdfs dfs -put /localfile /dir/file

copy from hdfs to local system:

    hdfs dfs -get /dir/file /localfile

delete files to trash:

    hdfs dfs -rm /dir/file

delete directory to trash:

    hdfs dfs -rm -r /dir

file and direcory size:

    hdfs dfs -du -h /dir/

check system for missing and wrong blocks:

    hdfs fsck /dir

hdfs administration:

    hdfs dfsadmin -<cmd>

hdfs statistic:

    hdfs dfsadmin -report

hdfs safemode:

    hdfs dfsadmin -safemode

hdfs block balancer:

    hdfs balancer
