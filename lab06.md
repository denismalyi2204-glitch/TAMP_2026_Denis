## Laboratory work VI

Данная лабораторная работа посвещена изучению средств пакетирования на примере **CPack**

## Report

Задаём окружение
```sh
export GITHUB_USERNAME=<имя_пользователя>
export GITHUB_EMAIL=<адрес_почтового_ящика>
alias edit=nano
alias gsed=sed
```

Клонируем и создаем репозиторий
```sh
cd ${GITHUB_USERNAME}/workspace
pushd .
source scripts/activate
git clone https://github.com/${GITHUB_USERNAME}/lab05 projects/lab06
cd projects/lab06
git remote remove origin
git remote add origin https://github.com/${GITHUB_USERNAME}/lab06
```
Вывод
```sh
Cloning into 'projects/lab06'...
remote: Enumerating objects: 102, done.
remote: Counting objects: 100% (102/102), done.
remote: Compressing objects: 100% (53/53), done.
remote: Total 102 (delta 26), reused 99 (delta 23), pack-reused 0 (from 0)
Receiving objects: 100% (102/102), 341.51 KiB | 1.93 MiB/s, done.
Resolving deltas: 100% (26/26), done
```


Редактируем cmakelists.txt
```sh
gsed -i '/project(print)/a\
set(PRINT_VERSION_MAJOR 0)
' CMakeLists.txt

gsed -i '/project(print)/a\
set(PRINT_VERSION_MINOR 1)
' CMakeLists.txt

gsed -i '/project(print)/a\
set(PRINT_VERSION_PATCH 0)
' CMakeLists.txt

gsed -i '/project(print)/a\
set(PRINT_VERSION_TWEAK 0)
' CMakeLists.txt

gsed -i '/project(print)/a\
set(PRINT_VERSION\
  \${PRINT_VERSION_MAJOR}.\${PRINT_VERSION_MINOR}.\${PRINT_VERSION_PATCH}.\${PRINT_VERSION_TWEAK})
' CMakeLists.txt

gsed -i '/project(print)/a\
set(PRINT_VERSION_STRING "v\${PRINT_VERSION}")
' CMakeLists.txt
```


Создаем описательные файлы
```sh
touch DESCRIPTION && edit DESCRIPTION   # добавить: "Print library for C++"
touch ChangeLog.md
export DATE="LANG=en_US date +'%a %b %d %Y'"
cat > ChangeLog.md <<EOF
* ${DATE} ${GITHUB_USERNAME} <${GITHUB_EMAIL}> 0.1.0.0
- Initial release
EOF
```


Конфигурация CPack — CPackConfig.cmake
```sh
cat > CPackConfig.cmake <<EOF
include(InstallRequiredSystemLibraries)

set(CPACK_PACKAGE_CONTACT ${GITHUB_EMAIL})
set(CPACK_PACKAGE_VERSION_MAJOR \${PRINT_VERSION_MAJOR})
set(CPACK_PACKAGE_VERSION_MINOR \${PRINT_VERSION_MINOR})
set(CPACK_PACKAGE_VERSION_PATCH \${PRINT_VERSION_PATCH})
set(CPACK_PACKAGE_VERSION_TWEAK \${PRINT_VERSION_TWEAK})
set(CPACK_PACKAGE_VERSION \${PRINT_VERSION})
set(CPACK_PACKAGE_DESCRIPTION_FILE \${CMAKE_CURRENT_SOURCE_DIR}/DESCRIPTION)
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "static C++ library for printing")

set(CPACK_RESOURCE_FILE_LICENSE \${CMAKE_CURRENT_SOURCE_DIR}/LICENSE)
set(CPACK_RESOURCE_FILE_README \${CMAKE_CURRENT_SOURCE_DIR}/README.md)

set(CPACK_RPM_PACKAGE_NAME "print-devel")
set(CPACK_RPM_PACKAGE_LICENSE "MIT")
set(CPACK_RPM_PACKAGE_GROUP "print")
set(CPACK_RPM_CHANGELOG_FILE \${CMAKE_CURRENT_SOURCE_DIR}/ChangeLog.md)
set(CPACK_RPM_PACKAGE_RELEASE 1)

set(CPACK_DEBIAN_PACKAGE_NAME "libprint-dev")
set(CPACK_DEBIAN_PACKAGE_PREDEPENDS "cmake >= 3.0")
set(CPACK_DEBIAN_PACKAGE_RELEASE 1)

include(CPack)
EOF
```


Подключение CPack в CMakeLists.txt
```sh
cat >> CMakeLists.txt <<EOF

include(CPackConfig.cmake)
EOF
```


Обновление README.md и фиксация
```sh
gsed -i 's/lab05/lab06/g' README.md
git add .
git commit -m "added cpack config"
git tag v0.1.0.0
git push origin master --tags
```
Вывод
```sh
On branch main
nothing to commit, working tree clean
fatal: tag 'v0.1.0.0' already exists
Username for 'https://github.com': denismalyi2204-glitch
Password for 'https://denismalyi2204-glitch@github.com': 
Enumerating objects: 109, done.
Counting objects: 100% (109/109), done.
Delta compression using up to 4 threads
Compressing objects: 100% (57/57), done.
Writing objects: 100% (109/109), 342.80 KiB | 114.27 MiB/s, done.
Total 109 (delta 29), reused 99 (delta 26), pack-reused 0
remote: Resolving deltas: 100% (29/29), done.
To https://github.com/denismalyi2204-glitch/lab06
 * [new branch]      main -> main
 * [new tag]         v0.1.0.0 -> v0.1.0.0
```


Создаем GitHub Actions workflow
```sh
mkdir -p .github/workflows
```


Создаём файл .github/workflows/cpack.yml
```sh
cat > .github/workflows/cpack.yml <<'EOF'
name: CPack Package Build

on:
  push:
    tags:
      - 'v*'
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v4
      with:
        fetch-depth: 0
    
    - name: Install dependencies
      run: |
        sudo apt-get update
        sudo apt-get install -y cmake build-essential
    
    - name: Configure CMake
      run: cmake -H. -B_build -DCMAKE_BUILD_TYPE=Release
    
    - name: Build project
      run: cmake --build _build
    
    - name: Create TGZ package
      run: |
        cd _build
        cpack -G "TGZ"
        cd ..
    
    - name: Create DEB package (optional)
      run: |
        cd _build
        cpack -G "DEB" || echo "DEB generation skipped"
        cd ..
    
    - name: Create RPM package (optional)
      run: |
        cd _build
        cpack -G "RPM" || echo "RPM generation skipped (rpmbuild not installed)"
        cd ..
    
    - name: List generated packages
      run: ls -la _build/*.tar.gz _build/*.deb _build/*.rpm 2>/dev/null || true
    
    - name: Upload artifacts
      uses: actions/upload-artifact@v4
      with:
        name: packages
        path: |
          _build/*.tar.gz
          _build/*.deb
          _build/*.rpm
        if-no-files-found: warn
EOF
```


Добавляем workflow в репозиторий
```sh
git add .github/workflows/cpack.yml
git commit -m "add GitHub Actions workflow for CPack"
git push origin master
```
Вывод
```sh
On branch main
nothing to commit, working tree clean
Username for 'https://github.com': denismalyi2204-glitch
Password for 'https://denismalyi2204-glitch@github.com': 
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 911 bytes | 911.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/denismalyi2204-glitch/lab06
   e4beec7..0e5772b  main -> main
```


Собираем проект
```sh
cmake -H. -B_build
cmake --build _build
cd _build
cpack -G "TGZ"
cd ..
mkdir -p artifacts
mv _build/*.tar.gz artifacts/
tree artifacts
```
Вывод
```sh
-- Configuring done (0.0s)
-- Generating done (0.0s)
-- Build files have been written to: /home/ubumba64/denismalyi2204-glitch/workspace/projects/lab06/_build
[ 33%] Built target print
[ 66%] Built target example1
[100%] Built target example2
CPack: Create package using TGZ
CPack: Install projects
CPack: - Run preinstall target for: print
CPack: - Install project: print []
CPack: Create package
CPack: - package: /home/ubumba64/denismalyi2204-glitch/workspace/projects/lab06/_build/print-0.1.1-Linux.tar.gz generated.
artifacts
└── print-0.1.1-Linux.tar.gz

1 directory, 1 file
```

## Homework

Устанавливаем RPM
```sh
sudo apt-get update
sudo apt-get install -y rpm
```

Собираем DEB и RPM пакеты
```sh
cd ~/denismalyi2204-glitch/workspace/projects/lab06
rm -rf _build
mkdir _build && cd _build
cmake .. -DCMAKE_BUILD_TYPE=Release
cpack -G DEB
cpack -G RPM
ls -la *.deb *.rpm
```
Вывод
```sh
-- Configuring done
-- Generating done
CPack: Create package using DEB
CPack: - package: /home/ubumba64/.../print-0.1.1-Linux.deb generated.

CPack: Create package using RPM
CPack: - package: /home/ubumba64/.../print-0.1.1-Linux.rpm generated.

-rw-rw-r-- 1 ubumba64 ubumba64  688 Apr 20 16:46 print-0.1.1-Linux.deb
-rw-rw-r-- 1 ubumba64 ubumba64 5857 Apr 20 16:46 print-0.1.1-Linux.rpm
```


Создаём cpack.yml для автоматической сборки пакетов
```sh
cat > ~/denismalyi2204-glitch/workspace/projects/lab06/.github/workflows/cpack.yml <<'EOF'
name: CPack Package Build and Release

on:
  push:
    tags:
      - 'v*'
  workflow_dispatch:

jobs:
  build-and-release:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    
    steps:
    - uses: actions/checkout@v4
      with:
        fetch-depth: 0
    
    - name: Install dependencies
      run: |
        sudo apt-get update
        sudo apt-get install -y cmake build-essential rpm
    
    - name: Configure CMake
      run: cmake -H. -B_build -DCMAKE_BUILD_TYPE=Release
    
    - name: Build project
      run: cmake --build _build
    
    - name: Create packages
      run: |
        cd _build
        cpack -G "TGZ"
        cpack -G "DEB"
        cpack -G "RPM"
        cd ..
    
    - name: Create GitHub Release
      uses: softprops/action-gh-release@v1
      with:
        name: "Release ${{ github.ref_name }}"
        tag_name: ${{ github.ref_name }}
        body: |
          ## Solver Application ${{ github.ref_name }}
          
          ### 📦 Пакеты для установки:
          - **DEB** - для Ubuntu/Debian
          - **RPM** - для Fedora/RHEL
          - **TGZ** - архив с бинарными файлами
        draft: false
        prerelease: false
        files: |
          _build/*.deb
          _build/*.rpm
          _build/*.tar.gz
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
EOF
```

Коммитим изменения и создаём тега
```sh
cd ~/denismalyi2204-glitch/workspace/projects/lab06
git add .
git commit -m "Prepare for release"
git push origin main
git tag -a v1.0.0 -m "Release v1.0.0 - solver application packages"
git push origin v1.0.0
```
Вывод
```sh
[main f83dbc5] Prepare for release
 4 files changed, 37 insertions(+), 1 deletion(-)
 create mode 100644 artifacts/print-0.1.1-Linux.tar.gz
 delete mode 100644 artifacts/screenshot.png
 create mode 100755 check_lab06.sh

To https://github.com/denismalyi2204-glitch/lab06
 * [new tag]         v1.0.0 -> v1.0.0
```

Проверяем статус сборки
```sh
gh run list -R denismalyi2204-glitch/lab06 --limit 3
```
Вывод
```sh
STATUS  TITLE                WORKFLOW             BRANCH  EVENT  ID           ELAPSED  AGE
*       Prepare for release  CPack Package Build  v1.0.0  push   24679173586  0s       less than a minute ago
*       Prepare for release  CI                   v1.0.0  push   24679173584  0s       less than a minute ago
*       Prepare for release  CI                   main    push   24679163325  12s      less than a minute ago
```

Проверяем работу workflow
```sh
gh run watch -R denismalyi2204-glitch/lab06
```
Вывод
```sh
✓ v1.0.0 CPack Package Build · 24679173586
Triggered via push less than a minute ago

JOBS
✓ build in 25s (ID 72171434659)
  ✓ Set up job
  ✓ Checkout code
  ✓ Install dependencies
  ✓ Configure CMake
  ✓ Build project
  ✓ Create TGZ package
  ✓ Create DEB package (optional)
  ✓ Create RPM package (optional)
  ✓ List generated packages
  ✓ Upload artifacts

✓ Run CPack Package Build (24679173586) completed with 'success'
```

Структура созданного workflow
```sh
.github/workflows/cpack.yml
├── Триггер: push tags (v*)
├── Сборка на ubuntu-latest
├── Установка зависимостей (cmake, rpm)
├── Конфигурация CMake
├── Сборка проекта
├── Создание пакетов (TGZ, DEB, RPM)
└── Создание GitHub Release с загрузкой пакетов
```