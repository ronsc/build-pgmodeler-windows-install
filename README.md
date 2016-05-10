## Pre-Require
- [postgresql(9.5)](http://www.enterprisedb.com/postgresql-952-installers-win64?ls=Crossover&type=Crossover) (Install Path) -> C:\PostgreSQL\9.5\
- [qt(5.5.1)](http://download.qt.io/official_releases/qt/5.5/5.5.1/qt-opensource-windows-x86-mingw492-5.5.1.exe) (Install Path) -> C:\Qt\Qt5.5\
- [xml2(2.7.8.win32) library](http://xmlsoft.org/sources/win32/libxml2-2.7.8.win32.zip) (Extract Path) -> C:\Qt\Qt5.5\5.5.1\mingw49_32\include [Folder Name: libxml]
- [pgmodeler(v0.8.2-beta1) source code](https://github.com/pgmodeler/pgmodeler/archive/v0.8.2-beta1.zip)

## Setup Step
1. Setup All Pre-Require
2. Add path Environments --> $PATH;C:\PostgreSQL\9.5\bin;C:\Qt\Qt5.5\5.5.1\mingw49_32\bin;
3. in file (pgmodeler.pri) change path of PGSQL_LIB, PGSQL_INC, XML_INC, XML_LIB
```shell
    windows {
      !defined(PGSQL_LIB, var): PGSQL_LIB = C:/PostgreSQL/9.5/lib/libpq.dll
      !defined(PGSQL_INC, var): PGSQL_INC = C:/PostgreSQL/9.5/include
      !defined(XML_INC, var): XML_INC = C:/Qt/Qt5.5/5.5.1/mingw49_32/include
      !defined(XML_LIB, var): XML_LIB = C:/Qt/Qt5.5/5.5.1/mingw49_32/include/libxml/bin/libxml2.dll
      ...
    }
```
4. Extract pgmodeler(v0.8.2-beta1) source code --> and rename to **pgmodeler**
5. Open bash cmd to pgmodeler root path and run
```shell
$ ./windeploy.sh
```
6. Install File Save to ./dist/
