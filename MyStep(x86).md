x86

1. download from https://downloads.mysql.com/archives/c-c/

    > mysql-connector-c-6.1.11-win32.msi

2. I install to default path (C:\Program Files (x86)\MySQL\MySQL Connector C 6.1)

3. use MinGW 7.3.0 (32-bit)

    - cd $QTDIR\Src\qtbase\src\plugins\sqldrivers
    
        > my path is D:\Qt5.14.2\5.14.2\Src\qtbase\src\plugins\sqldrivers
    
    - qmake sqldrivers.pro
    
    - cd to mysql
    
        - vi mysql.pro
        
        ```
        #QMAKE_USE += mysql
        ```
        
        and add the following setting
        
        ```
        LIBS += -L"C:\Program Files (x86)\MySQL\MySQL Connector C 6.1\lib" -llibmysql

        INCLUDEPATH += "C:\Program Files (x86)\MySQL\MySQL Connector C 6.1\include"

        DEPENDPATH += "C:\Program Files (x86)\MySQL\MySQL Connector C 6.1\include"
        ```
        
        - qmake mysql.pro
        
        - find qsqlmysql.dll in $QTDIR\Src\qtbase\src\plugins\sqldrivers\plugins\sqldrivers
        
            > my path is D:\Qt5.14.2\5.14.2\Src\qtbase\src\plugins\sqldrivers\plugins\sqldrivers
        
        - copy qsqlmysql.dll to $QTDIR\mingw73_32\plugins\sqldrivers
        
            > my path is D:\Qt5.14.2\5.14.2\mingw73_32\plugins\sqldrivers
