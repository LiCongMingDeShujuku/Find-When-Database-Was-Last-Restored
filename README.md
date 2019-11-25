![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 查找上次还原数据库的时间
#### Find When Database Was Last Restored
**发布-日期: 2014年4月23日 (评论)**

![#](images/##############?raw=true "#")

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
你可以查看上次还原数据库的时间，以及执行还原的用户（或运行还原操作的帐户）。 只需运行这个简单的脚本。 结果还将显示还原操作的“类型”。


## English
You can see when the database was last restored, and who performed the restore ( or under what account the restore operation was run ). Just run this simple script. The results will also show you the ‘type’ or restore that was run.

---
## Logic
```SQL
use msdb;
set nocount on
select
‘restore date’ = convert(char, restore_date, 9) , ‘destination database’ = destination_database_name
, [user_name]
, ‘restore type’ =
case restore_type
when ‘D’ then ‘Database Restore’
when ‘F’ then ‘File Restore’
when ‘G’ then ‘Filegroup Restore’
when ‘I’ then ‘Differential Restore’
when ‘L’ then ‘Log Restore’
when ‘V’ then ‘Verifyonly’
end
from
msdb..restorehistory
order by
restore_date desc


```



[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

