# Test cases

When it is important to make a testing artefact that should be easy to follow to and cause no discrepancies, one should use test cases. It is an algorithm of steps with expected results. When necessary, pre-requisites included. It could be written on a checklist base, where only the idea of a test had been given.

## Overview

There is a system for a tester called «Интернет-банк i2B» («Internet-bank i2B»), available [here](https://idemo.bspb.ru/). It features a lot of functions representing a real bank web application. Most of functions are described in [documentation](https://bspb.ru/media/rukovodstvo_polzovatelja_i2_B_945386ba7f.pdf). There are incongruities in it, and it is not clear if they are deliberate or not. Anyhow, I will take these as a bugs. Let's make two actions inside the system:

1. Authorize in, and then log out
2. Form a bank statement and export it

## Test case #1

**Summary**: Authorizing in and logging out of system

**ID**: Bank01

**Class**: Smoke

| Step                                                                                    | Expected result                                               |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------|
| 1. Visit https://idemo.bspb.ru/                                                         | Page loads, authorizing fields appear                         |
| 2. Enter login: "demo" and password: "demo", hit "Войти"                                | One time code field appears, SMS arrives                      |
| 3. Enter one time code and finish authorization                                         | Page "Обзор" loads                                            |
| 4. Hit the red cross at the right top page corner                                       | Authorization page loads                                      |

**Actual results match.**

## Test case #2

**Summary**: Forming a bank statement (выписка) and exporting it

**ID**: Bank02

**Class**: Critical Path

**Prerequisites**: User is authorized and page "Обзор" is loaded

| Step                                                                                    | Expected result                                               |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------|
| 1. Hover cursor over "Счета" tab                                                        | Pop-up menu with "Выписка" item appears                       |
| 2. Hit "Выписка"                                                                        | New page loads                                                |
| 3. Choose the reqiured (any) account in drop-down menu                                  | Menu updates                                                  |
| 4. Choose the begining of period date with calendar                                     | Calendar updates                                              |
| 5. Choose the end of period date with calendar                                          | Calendar updates                                              |
| 6. Check "Краткая выписка" item                                                         | Item checks                                                   |
| 7. Hit "Получить" button                                                                | Page updates, bank statement appears                          |
| 8. Hit "Экспорт" button                                                                 | Menu to save a PDF appears                                    |

**Actual results**:

 Step 3 result won't match: Menu updates, but page updates before button "Получить" is hit.

 Step 6 result won't match: The item " Краткая выписка" is absent.
