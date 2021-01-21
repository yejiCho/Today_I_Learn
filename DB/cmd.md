# 명령어

- C드라이브 의 .exe 확장자에 해당하는 파일목록을 전부 찾기

```
where /r c:\ *.exe
```

- 출력된 파일목록을 filelist.txt 파일로 저장하기

```
where /r c:\ *.exe >> filelist.txt

```

## 데이터베이스 백업하기

1. 명령프롬프트 실행
2. 디렉토리 이동

```
cd C:\Program Files\PostgreSQL\11\bin
```

3. 데이터베이스 복원

```
pg_dump.exe -h 127.0.0.1(IP주소) -p 5432(PORT) -U postgres(계정) -Fc -d TEST(DB명) -f c:\example_20201220.backup (backup file location)
```

4. .sql 파일 실행

```
psql -h 127.0.0.1 -p 5432 -U postgres -d TEST < c:\example_20201220.sql
```



- [Failed to open the system default web browser error solution when opening PostgreSQL after installation](https://www.programmersought.com/article/63604577822/)

- [pgadmin4 윈도우 접속](https://postgresql.kr/blog/postgresql_for_windows.html)