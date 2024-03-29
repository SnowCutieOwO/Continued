# 配置
###### **这个配置会以几部分的方式来呈现在你面前，如果每个配置选项你觉得不明白，不知道怎么描述，那么你可以在config.yml这个文件里找到对应的选项 **

  
## claimingEnabled
启用了这个选项，那么/season claim这条指令将会启用，一般情况下是true
但你要启用了MySQL就可以把插件放到子服当中，且允许奖励转移到非装有此插件的子服，很明显，若禁用MySQL那么这个指令就只能在一个服务器使用不能相同。
还有一点你要注意，即使不用MySQL而是用SQLite这个选项
你也可以将这个插件的数据库文件拷贝到任何装有此插件的子服，启用claimingEnabled给玩家提供兑换内容
***
  
## trackingEnabled(这是个危险操作，请先阅读下面)
  
这个称为“跟踪”属于此插件的功能，能跟踪其他玩家放置的每个容器，
包括陷阱箱，大箱子，熔炉，桶和其他玩家背包栏里的物品。若在服务器上使用此插件，只是为了领取物品，那么你就要禁用这个选项，否则会导致破坏性的情况。
此插件本身是需要删除世界再重新生成的，还有管理玩家背包栏，好比背包栏，还有末影箱储存的物品
在两个赛季中间的时候，会破坏掉末影箱还有物品栏里的内容
同时会招来玩家的不理解和辱骂
如果你是无意中将这个选项打开，只要在配置文件中禁用再重新启动服务器，就可以了
同时你还要删掉seasons_worlds这个文件夹
***
## persistSeasonalWorlds

很明显，这个选项当初被设计出来是让~~op~~管理员 来决定在新一季度的对决赛开始的时候保留当前的地图
默认选项为true，若你的储存空间有限，那么你需要禁用此选项，但不会删除当前这一季度的地图
***
## unloadPastSeasons

这个选项可以“卸载”过去任何一季度的旧地图，能让服务器不会加载旧地图，但是你若想使用persistSeasonalWorlds这个选项
但又不想加载这些旧的世界，那么这个选项就很有用，如果持久化被禁止使用，那么这个选项就会没有任何作用
***
## minSeasonLength

下面这几个选项，可以根据服务器情况进行配置以运行此插件，对于小型服务器minSeasonLength这个选项是会有帮助的
因为你不想让玩家打到一半就结束赛季
在插件内，称之为Soft End Date
意味着在玩家没打完之前，不管活下来几个玩家，这个插件都不会创建新的赛季
***
## maxSeasonLength

和minSeasonLength不同，这个选项可以是负值，设置成-1就等于完全禁用
目的是为了让此插件发挥最大的功效，同时有不同风格的赛季
若你开启了这个选项，将会从赛季创建的日期开始延长。当时候到了，不管玩家有多少，此赛季都会结束

赛季若以这种方式结束，那么你要注意一下
首先，此插件将考虑玩家的join_date和lastonline的时候会将时间也给算进去
该赛季生成的所有奖励以及物品，将在胜利者中进行分配，最高可到maxSurvivorsRemaining这个选项里的值
再比如说，如果你有10名胜利者，但是maxSurvivorsRemaining这里的值如果为2
那么就会选择第一和第二名玩家，在这两个玩家中平均分配
但是如果无法实现平分，那么就会将剩余部分交给排行榜上的玩家，即使前两名排行榜玩家的生存时间相同
也会抛去剩余时间（希望不会被下界合金块阻挡lol）
***
## maxSurvivorsRemaining

剩下来的幸存者数量设置这个表面上很简单，要是开发到极致，会将搞出很多有趣的功能
对于那些新手来说默认选项为1
这就表示若达到minSeasonLength设置的值，那么服务器后台将不会用表明的方式结束本赛季
直到剩下最后一个幸存者     
理论上来说，可以将这个设置为0
但这样做的话，服务器不会产生任何奖励给玩家
而当最后一名玩家死亡后，本赛季将会立刻结束
同时这个值设置的太高也不是什么最好的解决方式。因为这样你的玩家将会频繁“投票”才能继续，或者结束本赛季
然而，这个取决于你用不用这个选项
***
## minVotesToEndSeason

若想要赛季快速结束，是需要最低投票率的
默认情况下通过lastLoginThreshold以确定玩家对计算的“有效”百分比
换句话来说玩家若三天不活跃（默认设置）那么他们的投票不会计入百分比内
一名玩家完全可能因为不活跃而从名单上被挤掉，会在本赛季自动触发将赛季结束
预期表现是这样的
***
## lastLoginThreshold

这些是希望玩家参加“活动”天数
如果玩家的last_online日期超过阈值，那么玩家们将获取不到奖励，也不能参与投票
目的在于，让玩家赛季中保持活跃，这是作为服主控制活动平衡的一种方式
***
## notificationInterval

设置玩家会收到通知的间隔 /season vote continue 或者 /season vote end
到了minSeasonLength设定的日期且minSurvivorsRemaining小于等于所需要的数量之前，玩家不会接收到投票通知
玩家可以修改投票，在下一次赛季周期，会重新季赛按投票百分比
***
## voteResetInterval

重新设置提示玩家投票时间间隔，尽管玩家可以在任何时间投票，但这个选项会提醒玩家投票时间隔不超过多少多少
没有投票的玩家在此赛季结束的时候不会被算在内，如果这些玩家很活跃，那么他们还会获得奖励
***
## endOfSeasonCommands

并没有做这个选项，放到这里只是为了将来能在未来版本更新中加入进去
但是直到我把这个选项放入到此插件里，这个选项只会实现；冷却这个功能。
***
## Storage Types

此插件支持MySQL和SQLite但是这两种都会让我心烦意乱，而且兼容性不太行，如果出现了数据库报错问题，请告诉我，我会尽快解决这个问题
MySQL和SQLite功能上近乎一样，若你想在不同的子服上让玩家领取奖励，你可以将hardcoreseasons.db这个数据库文件放到你的子服里，或者使用MySQL
很显然，最好的办法是MySQL，若你想只在单端上让玩家领取季节性奖励，那么SQLite就是百分之百你可以选择的数据库

###### 此插件不会细说，因为其他插件都解释了与此插件的区别，我这么跟你说吧，我相信你能做到把这个插件玩法搞到极致！





