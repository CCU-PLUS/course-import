# CCU PLUS Course Import Package Spec

Provide artisan commands for core module to import course data to database from National Chung Cheng University.

## Spec Version

0.0.1 (2019/01/08)

## Command Spec

### course:import

import course data to database, showing imported courses number when command executed successfully

#### command arguments

|  field   |  type  | required | multiple |     default      | example |                   remark                    |
| :------: | :----: | :------: | :------: | :--------------: | :-----: | :-----------------------------------------: |
| semester | string |    -     |    ✓     | current semester |  1071   | semesters that will be imported to database |

#### command options

|  option   |                            remark                            |
| :-------: | :----------------------------------------------------------: |
|  --force  | import course data even if the semester was already imported |
| --dry-run | output course data which will be imported instead of importing it |

#### exceptions

- `UnexpectedValueException` - invalid semester value or semester is not exist
- `RuntimeException` - network error or target website is not available