# Jest coverage bug with identical files

Run the following command twice:
```bash
$ npm test -- --coverage
```

Expected:
```
------------|----------|----------|----------|----------|----------------|
File        |  % Stmts | % Branch |  % Funcs |  % Lines |Uncovered Lines |
------------|----------|----------|----------|----------|----------------|
All files   |      100 |      100 |      100 |      100 |                |
 a          |      100 |      100 |      100 |      100 |                |
  Header.js |      100 |      100 |      100 |      100 |                |
 b          |      100 |      100 |      100 |      100 |                |
  Header.js |      100 |      100 |      100 |      100 |                |
------------|----------|----------|----------|----------|----------------|
```
Actual
```
------------|----------|----------|----------|----------|----------------|
File        |  % Stmts | % Branch |  % Funcs |  % Lines |Uncovered Lines |
------------|----------|----------|----------|----------|----------------|
All files   |     12.5 |        0 |    33.33 |       25 |                |
 a          |      100 |      100 |      100 |      100 |                |
  Header.js |      100 |      100 |      100 |      100 |                |
 b          |        0 |        0 |        0 |        0 |                |
  Header.js |        0 |        0 |        0 |        0 |         1,5,10 |
------------|----------|----------|----------|----------|----------------|
```
