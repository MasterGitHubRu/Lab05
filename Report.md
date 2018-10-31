## Laboratory work V

Данная лабораторная работа посвещена изучению систем непрерывной интеграции на примере сервиса **Travis CI**

```ShellSession
$ open https://travis-ci.org
```

## Tasks

- [x] 1. Авторизоваться на сервисе **Travis CI** с использованием **GitHub** аккаунта
- [x] 2. Создать публичный репозиторий с названием **lab05** на сервисе **GitHub**
- [x] 3. Ознакомиться со ссылками учебного материала
- [x] 4. Включить интеграцию сервиса **Travis CI** с созданным репозиторием
- [x] 5. Получить токен для **Travis CLI** с правами **repo** и **user**
- [x] 6. Получить фрагмент вставки значка сервиса **Travis CI** в формате **Markdown**
- [x] 7. Установить [**Travis CLI**](https://github.com/travis-ci/travis.rb#installation)
- [x] 8. Выполнить инструкцию учебного материала
- [x] 9. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```ShellSession
$ export GITHUB_USERNAME=<имя_пользователя> //создаем перменную с именем пользователя на ГитХаб
$ export GITHUB_TOKEN=<полученный_токен> //создаем переменную с токеном
```

```ShellSession
$ cd ${GITHUB_USERNAME}/workspace //переходим в каталог
$ pushd . //сохранить текущий каталог в памяти 
~/Kutyirov/workspace ~/Kutyirov/workspace

$ source scripts/activate //выполнить скрипты
```

```ShellSession
$ \curl -sSL https://get.rvm.io | bash -s -- --ignore-dotfiles //переход по ссылке (если можно - с шифрованием) + считать комманды со стандартного ввода
Turning on ignore dotfiles mode.
Downloading https://github.com/rvm/rvm/archive/master.tar.gz
Installing RVM to /Users/mac/.rvm/
Installation of RVM in /Users/mac/.rvm/ is almost complete:

* To start using RVM you need to run `source /Users/mac/.rvm/scripts/rvm`
in all your open shell windows, in rare cases you need to reopen all shell windows.

$ echo "source $HOME/.rvm/scripts/rvm" >> scripts/activate //выводим текст
$ rvm autolibs disable //отключаем autolibs
$ rvm install ruby-2.4.2 //установка ruby версии 2.4.2
Searching for binary rubies, this might take some time.
No binary rubies available for: osx/10.13/x86_64/ruby-2.4.2.
Continuing with compilation. Please read 'rvm help mount' to get more information on binary rubies.
Installing Ruby from source to: /Users/mac/.rvm/rubies/ruby-2.4.2, this may take a while depending on your cpu(s)...
ruby-2.4.2 - #downloading ruby-2.4.2, this may take a while depending on your connection...
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
Dload  Upload   Total   Spent    Left  Speed
100 12.0M  100 12.0M    0     0  1343k      0  0:00:09  0:00:09 --:--:-- 1609k
ruby-2.4.2 - #extracting ruby-2.4.2 to /Users/mac/.rvm/src/ruby-2.4.2.....
ruby-2.4.2 - #configuring.....................................................|-
.....
ruby-2.4.2 - #post-configuration.
ruby-2.4.2 - #compiling.............................................../
.....................................
ruby-2.4.2 - #installing.......
ruby-2.4.2 - #making binaries executable..
ruby-2.4.2 - #downloading rubygems-2.7.6
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
Dload  Upload   Total   Spent    Left  Speed
100  832k  100  832k    0     0   599k      0  0:00:01  0:00:01 --:--:--  598k
ruby-2.4.2 - #extracting rubygems-2.7.6.....
ruby-2.4.2 - #removing old rubygems........
ruby-2.4.2 - #installing rubygems-2.7.6..........................
ruby-2.4.2 - #gemset created /Users/mac/.rvm/gems/ruby-2.4.2@global
ruby-2.4.2 - #importing gemset /Users/mac/.rvm/gemsets/global.gems............there was an error installing gem rubygems-bundler
....................
ruby-2.4.2 - #generating global wrappers.......
ruby-2.4.2 - #gemset created /Users/mac/.rvm/gems/ruby-2.4.2
ruby-2.4.2 - #importing gemsetfile /Users/mac/.rvm/gemsets/default.gems evaluated to empty gem list
ruby-2.4.2 - #generating default wrappers.......
ruby-2.4.2 - #adjusting #shebangs for (gem irb erb ri rdoc testrb rake).
Install of ruby-2.4.2 - #complete 
Ruby was built without documentation, to build it run: rvm docs generate-ri

$ rvm use 2.4.2 --default //используем версию 2.4.2
Using /Users/mac/.rvm/gems/ruby-2.4.2
$ gem install travis //устанавливаем travis (использую brew)
Updating Homebrew...
==> Auto-updated Homebrew!
Updated 1 tap (homebrew/core).
==> New Formulae
meson-internal             php-code-sniffer           phpunit
==> Updated Formulae
abcmidi                    libdill                    percona-xtrabackup
agedu                      libepoxy                   php@7.1
amber                      libgweather                pipenv
armor                      libhttpseverywhere         pipes-sh
artifactory                libidn                     pre-commit
autopep8                   libmpdclient               presto
bcpp                       libosmium                  proj
coffeescript               libressl                   psqlodbc
diffoscope                 libsecret                  python
docfx                      libusb                     re2
dscanner                   libvirt                    reminiscence
dynamips                   lmdb                       rust
ejabberd                   metabase                   s6
fuse-emulator              mkvtoolnix                 sbcl
g3log                      modules                    sip
gitbucket                  nano                       sjk
glibmm                     nativefier                 skaffold
gnu-sed                    newsboat                   skinny
go                         node                       sqlmap
go-jira                    node-build                 sysbench
gobject-introspection      node@4                     sysdig
godep                      node@6                     tbb
gom                        node@8                     terragrunt
grakn                      open-mpi                   tmuxinator-completion
graphene                   openshift-cli              unrar
gutenberg                  openttd                    unyaffs
hledger                    osmium-tool                vim
http-parser                osquery                    vim@7.4
jenkins                    pandoc-crossref            watch
jpegoptim                  parallelstl                webpack
kubectx                    pdnsrec                    xmount
==> Renamed Formulae
php56 -> php@5.6

==> Downloading https://homebrew.bintray.com/bottles/travis-1.8.8_2.high_sierra.
==> Downloading from https://akamai.bintray.com/d2/d25cfab9d040ecce4189e64702aa9
######################################################################## 100.0%
==> Pouring travis-1.8.8_2.high_sierra.bottle.tar.gz
🍺  /usr/local/Cellar/travis/1.8.8_2: 2,859 files, 11.9MB
```

```ShellSession
$ git clone https://github.com/${GITHUB_USERNAME}/lab04 projects/lab05 //клонируем репозиторий
Cloning into 'projects/lab05'...
remote: Counting objects: 24, done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 24 (delta 4), reused 17 (delta 2), pack-reused 0
Unpacking objects: 100% (24/24), done.

$ cd projects/lab05 //переходим в каталог
$ git remote remove origin //управление репозиторием
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab05 //добавляем репозиторий
```

```ShellSession
$ cat > .travis.yml <<EOF //вставляем в файл следующие строки (до встречи EOF)
language: cpp
EOF
```

```ShellSession
$ cat >> .travis.yml <<EOF //вставляем в файл следующие строки (до встречи EOF)

script:
- cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
- cmake --build _build
- cmake --build _build --target install
EOF
```

```ShellSession
$ cat >> .travis.yml <<EOF //вставляем в файл следующие строки (до встречи EOF)

addons:
  apt:
    sources:
      - george-edison55-precise-backports
    packages:
      - cmake
      - cmake-data
EOF
```

```ShellSession
$ travis login --github-token ${GITHUB_TOKEN} //логинимся на Трэвисе
Ignoring gem-wrappers-1.4.0 because its extensions are not built.  Try: gem pristine gem-wrappers --version 1.4.0
Successfully logged in as Kutyirov!
```

```ShellSession
$ travis lint //выводит предупреждения для .travis.yml
Ignoring gem-wrappers-1.4.0 because its extensions are not built.  Try: gem pristine gem-wrappers --version 1.4.0
Warnings for .travis.yml:
[x] value for addons section is empty, dropping
[x] in addons section: unexpected key apt, dropping

```

```ShellSession
$ ex -sc '1i|<фрагмент_вставки_значка>' -cx README.md //открыть в текст.ред. ex, записать фрагмент в README.md в начале файла
```

```ShellSession
$ git add .travis.yml //добавить файл
$ git add README.md //добавить файл
$ git commit -m"added CI" //создать коммит
[master ea1207c] added CI
2 files changed, 13 insertions(+)
create mode 100644 .travis.yml

$ git push origin master //загрузть на ГитХаб
Counting objects: 28, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (22/22), done.
Writing objects: 100% (28/28), 8.58 KiB | 731.00 KiB/s, done.
Total 28 (delta 6), reused 0 (delta 0)
remote: Resolving deltas: 100% (6/6), done.
To https://github.com/Kutyirov/lab05
* [new branch]      master -> master


```

```ShellSession
$ travis lint //вывод предпуреждений для .travis.yml
Warnings for .travis.yml:
[x] value for addons section is empty, dropping
[x] in addons section: unexpected key apt, dropping

$ travis accounts //показать аккаунты и их статус
Kutyirov (Robert): subscribed, 4 repositories

$ travis sync //новая синхронизация с ГитХаб
synchronizing: . done

$ travis repos //список репозиториев
Kutyirov/lab03 (active: no, admin: yes, push: yes, pull: yes)
Description: ???

Kutyirov/lab04 (active: no, admin: yes, push: yes, pull: yes)
Description: ???

Kutyirov/lab05 (active: no, admin: yes, push: yes, pull: yes)
Description: ???

Kutyirov/vector_example (active: yes, admin: yes, push: yes, pull: yes)
Description: ???

$ travis enable //включить проект
Detected repository as Kutyirov/lab05, is this correct? |yes| yes
Kutyirov/lab05: enabled :)

$ travis whatsup //перечислить последние сборки
Kutyirov/vector_example passed: #13

$ travis branches //самая последняя сборка для каждой ветки
-
$ travis history //история сборок
-
$ travis show //отобразить сборку
no build yet for Kutyirov/lab05
```

## Result

```ShellSession
$ popd //возвращаем путь к вершине стека
~/Kutyirov/workspace
$ export LAB_NUMBER=05 //создаем переменную
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER} //клонируем репозиторий
Cloning into 'tasks/lab05'...
remote: Counting objects: 47, done.
remote: Total 47 (delta 0), reused 0 (delta 0), pack-reused 47
Unpacking objects: 100% (47/47), done.

$ mkdir reports/lab${LAB_NUMBER} //создаем папку
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md //копируем файлы
$ cd reports/lab${LAB_NUMBER} //переходим в каталог
$ edit REPORT.md //открывает отчет
$ gistup -m "lab${LAB_NUMBER}" //загружаем гит
```

## Links

- [Travis Client](https://github.com/travis-ci/travis.rb)
- [AppVeyour](https://www.appveyor.com/)
- [GitLab CI](https://about.gitlab.com/gitlab-ci/)
