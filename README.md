# Podstawy-Linux-sa
Comendy

Git powstał w 2005 roku (jego pierwszą wersję stworzył twórca Linuxa Linus Torvald, szwedzkojęzyczny Fin).
Git został napisany w języku C. Używa algorytmu SHA1, co czyni go też bardzo bezpiecznym (хэш, идентификаторфикатор).
  
Рабочий каталог
Промежуточная зона (индекс)
Папка Git (репозиторий Git) 

4 stany plików w репозиторий:
- nieśledzony (неотслеживаемый) <- gdy dodamy nowy plik (lub usuniemy ze śledzonych)
- śledzony niezmodyfikowany (отслеживается без изменений) <- pliki które zostały już dodane do repozytorium (gdy wykonamy commit) 
                                                   i od tego czasu w katalogu roboczym nie był zmieniany
- śledzony zmodyfikowany (отслеживается изменено) <- plik dodany wcześniej do repozytorium, aactualnie zmieniony (edytowany) w folderze roboczym
- śledzony w poczekalni (отслеживается постановка) <- plik, który został dodany do indeksu (сцена) i oczekuje na commit 

`` ''
$ git config -l
$ git config --global user.name "user_name"
$ git config --global user.email "user_email@users.noreply.github.com"

Удалить глобальную идентичность:

git config --global --remove-section имя_пользователя
git config --global --remove-section user.email

`` ''
## Общие команды git:
`` ''
$ git init <--- Tworzy nowe repozytorium с каталогом, w którym polecenie jest wywołane
$ git status
$ git add <имя_файла / каталога>
$ git status
$ git commit -m "Начальная фиксация"
$ git status
$ git журнал
$ git push origin master
$ git pull
$ gitk 
$ gitg

`` ''
`` ''
$ git --version
$ какая версия
$ git удаленное добавление источника https: // <your-git-service-address> /owner/repository.git
$ cd <путь, по которому клон должен создать каталог>
$ git clone https: //yourusername@bitbucket.org/username/projectname.git

Помогает команда:

$ git diff --help <появится страница руководства>
$ git help diff
$ git checkout -h
$ git-status (1) Страница руководства
$ apt-get install git
$ git log <отобразит все ваши коммиты с автором и хешем. 
                      Это будет отображаться в нескольких строках для каждой фиксации. >
$ git log --decorate --oneline --graph <Чтобы просмотреть журнал в более красивой графоподобной структуре>
$ git log --oneline <покажет все ваши коммиты только с первой частью хэша и сообщением о фиксации>
$ git shortlog <сводка журнала git и групп по авторам>
$ Чтобы просто увидеть количество коммитов и подавить описание коммита, передайте опцию сводки:
-s
--резюме
$ git shortlog -s
$ git log --all --grep "удаленный файл" <Будет искать строку удаленного файла во всех журналах во всех ветвях.>

$ git log --grep = "add file" --invert-grep <Показывает все коммиты, которые не содержат файл добавления.>
$ git log - после 01.05.2016

Псевдоним --after - --since.
Флаги существуют и для обратного: --before и --until.

$ git log --author = автор

$ git show 48c83b3690dfc7b0e622fd220f8f37c26a77c934 (номер фиксации)
$ git checkout -b <новая- ветка> <- создать новую ветку>
$ git checkout -b <новая ветка> <существующая ветка>
$ git rm filename <- удалить файл
$ git diff <- это многофункциональная команда Git, которая при выполнении запускает функцию сравнения с источниками данных Git. 
$ git diff 1234abc..6789def # старый новый
$ git status -v
Это вызовет подробные настройки команды статуса
Функция слияния $ git / add-gremlins

$ git commit --amend <--- Poprawki w ostatnim (najnowszym) commicie. Змяны ж
                           zawartości i сообщение, nowe metadane też.

$ git commit --amend -m "наше новое сообщение <--- Jeśli chcemy zmienić tylko komentarz, to możemy napisać tak

$ git log --oneline // w jednej linii podstawowe informacje
$ git log --oneline 10 // ile linii (od najnowszych)
$ git log - с "2019" // od 2019
$ git log --since = "5.4.2019" // конкретный данные; инным запиской

$ git log --grep <--- выполнение фиксации
$ git log --grep "plik.txt" <--- wyszukiwanie w message, wielkośc litre ma znaczenie
$ git log --grep = "delete" <--- jw, ale w innym zapisie

$ git log --stat <--- które pliki zmienił commit iw jaki sposób wyświetla listę commitów jak git log

$ git show <--- Co się zmieniło (szczegółowo) w danym commicie (wnajnowszym). Możemy też wskazać o jaki commit nam chodzi, np.
$ git показать 5b8d8d0febd48406dc3dcc93599e23177d60b01e
$ git показать 5b8d8d0

$ git diff (поровнание)
$ git diff nazwa-pliku <--- конкретный плик
$ git diff --cached <--- pliki w stage (pliki sledzone w poczekalni) z plikami z repozytorium
                            (domyślnie z tymi w HEAD, czyli ostatniego commitu w gałęzi). 
                            Zamiast cached można użyć też parameterru --staged, który robi dokładnie to samo.
                            Możliwość porównania plików w rónych commitach
$ git diff 852ff1d 962a5ab nazwa-pliku <--- porównanie wersji z commitów

$ git diff
$ git diff --staged
$ git diff назва-плику

$ git rm plik <--- Usuwa pliki z katalogu roboczego i wersję z indexu. Информация
                                       znajduje się w плацдарм (najbliższy commit to uwzględni). Информация
                                       o tym zobaczymy po wyświetleniu satusu repozytorium (статус git).
                                       Oczywiście nie usuwa takiego pliku z history w repozytorium.
$ git rm --cached plik <--- Usuwa pliki z indexu, ale nie z katalogu roboczego (по тым полечению плик ма стан nieśledzony).
                                       Można więc powiedzieć, że robi 1 z 2 etapów, które wykonuje git rm plik.
$ rm file <--- usuwa z katalogu roboczego.
$ git rm - кешированный файл <- usuwamy z indexu.
$ git rm file <--- usuwa z katalogu roboczego iz indexu.

$ git mv index.txt index.html
                                         <--- Zamiana nazwy pliku. Przy czym w praktyce widzimy, że mamy
                                         Задание переименовано в w następnym commicie, które oznacza
                                         Polecenie usunięcia jednego pliku i dodania nowego.
                                         
$ git checkout plik <--- Zmiany z wersji roboczej są usuwane i przywracana jest (w katalogu roboczym) wersja,
                                        które znajduje się w indeksie. W praktyce jeśli nie mamy żadnej zmiany w плацдарм
                                        to wersja jaka była po ostatnim commicie
$ git checkout - plik <--- lepiej tak git checkout - plik, niż tak: git checkout plik
                                        Bezpieczniej z dwoma kreskami po poleceniu checkout. Bez dwóch
                                        kresek Git nie zawsze uzna, ze kolejnym parameter będzie plik.
$ git checkout - * .txt
$ git checkout HEAD - plik <--- do katalogu roboczego przywracana jest wersja pliku z ostatniego commita

$ git checkout 5a33dd2
                                        <--- Przywrócenie indexu z tego commitu. W praktyce nasz каталог
                                        roboczy po takiej operacji będzie się składał z indexu w chwili
                                        wykonania commita o danym identityfikatorze.
$ git checkout id-commita <- ustawienie HEAD na tym commicie
$ git checkout nazwa-brancha <- przełączenie na inną gałąź

$ git reset / git reset HEAD
                                        <--- Usuwa pliki ze плацдарм (pliki są nadal śledzone i są oczywiście w katalogu roboczym).
                                        Przywracamy stan indeksu do stanu po ostatnim commicie, więc
                                        wszystko co dodaliśmy do indeksu (плацдарм, poczekalnia) już się po tej operacji w nim nie znajduje.
                                        Użycie wskaźnika HEAD jest czytelniejsze, wiemy do czego wracamy (stanu po ostatnim commicie). 
                                        Ponadto możemy Spojnie użyć po nim ścieżki dio pliku (przy użycie po reset mogą być problemy i wtedy lepiej
$ git reset - название плику

$ git reset / git reset HEAD
$ git сбросить
$ git сбросить HEAD
                                        <--- Alternatywnie wskazujemy plik / pliki / katalog, którego zmiany
                                        chcemy usunąć ze плацдарм (przywrócić pierwotną wersję).
$ git reset - плик
$ git сбросить HEAD plik

$ git rm plik <--- usuwa plik z indexu (область подготовки) из каталога робочего
$ git rm --cached plik <--- usuwa plik z indexu, plik staje się nieśledzony.
$ git checkout - plik <--- do katalogu roboczego przywracana jest wersja, która znajduje się aktualnie w indexie
$ git reset HEAD plik <--- usuwa z indexu zmiany (przywracamy do indeksu wersję jaka była po statnim commicie)

$ .gitignore <--- Określamy listę plików i folderów, które nie trafią do repozytorium.
                                        .gitignore obejmie tylko pliki nieśledzone, więc każdy nowo dodany plik (каталог z
                                        plikami), był ignorowany, musimy dodać do .gitignore. Jeśli pliki są już
                                        śledzone, musimy zmienić ich stan na nieśledzony). 
                                        
gałąź мастер

$ git branch <--- Na jakim branchu (gałęzi) się znajdujemy. Początkowo mamy jedną gałąż z nazwą master. По wpisaniu git
                                        филиал dostaniemy informację o istniejących gałęziach (by to zobaczyć wcześniej musimy zrobić choć jeden commit)
                                        
филиалы - gałęzie

Gał główna - мастер (pierwsza gałąź w naszym repozytorium)

Tworzenie osobnych gałęzi służy rozwijaniu niezależnych / testowych / pobocznych elementów projektu.

Gałęzie mogą być scalane - слияние
Gałęzie mog mieć zupełnie róną zawartość.

$ git branch <--- lista wszystkich branchów
$ git branch <--- nazwa-nowego-brancha // tworzymy nową gałąź
$ git checkout nazwa-istniejącego-brancha <--- przełączamy się na inną gałąź
$ git merge nazw-brancha <--- łczenie gałęzi na której jesteśmy ze wskazaną gałęzią

$ Git push <--- прогнозирование zmian z jednego repozytorium (naszego lokalnego)
                                        делать иннего репозиториум (здального)
                                        
$ Git pull <--- Pobieranie zmian z jednego repozytoriu (zdalnego) na inne (nasze lokalne).
                                        Nasze sklonowane repozytorium jest aktualizowane
`` ''

Эдиторий

vim - zaawansowany edytor tekstowy w trybie tekstowym

Vi iMproved - nowa wersja znanego edytora Vi. Posiada

    podświetlanie składni dla wielu języków programowania
    możliwość edycji kilku plików na raz
    Богатего хелпа
    bardzo zaawansowane funkcje edycji
Чтобы выйти из редактора vi без сохранения внесенных вами изменений:
Если вы сейчас находитесь в режиме вставки или добавления, нажмите Esc.
Нажмите: (двоеточие). Курсор должен снова появиться в нижнем левом углу экрана рядом с подсказкой с двоеточием.
Введите следующее: q!
Это закроет редактор, и все изменения, внесенные в документ, будут потеряны.

Вставить - Esc - Esc -i
: w [newfilename] - переименовать существующий файл, добавив новое имя после команд.
: wq - сохранить файл и выйти из текстового редактора
: x - Это сохранит изменения и выйдет
: q! - выйти без сохранения изменений
