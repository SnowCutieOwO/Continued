# 配置文件&信息

```yaml
#
# BLACKJACK
#      by Perotin
#注释汉化：RaymondChang(mcbbs:オビト)

# 如果你希望用vault的经济功能那么就写true, 反之要用经验代替经济插件就填写false
cash-or-xp: true
# 是否让这个玩家允许下注比自己还要大的金额
bet-overflow: false
# 如果上面写的为true那么这里就能调整他们下注最大的金额
bet-overflow-max: 1000

# 收取赌金税和扣除的百分比 设置0.0代表不用交税，设置范围从0.0到100.0 
tax-percent: 0.0

# 设置一个最大投注和最小投注金额，任意一项设置为0那么就没法投
bet-min: 0.0
bet-max: 0.0

#下面的选项与放弃下注的选项有关

# 是否放弃此次赌注 (放弃赌注且抽取百分之几的赌金)
enable-surrender: true

# 服务器会抽取多少赌金(0-99)
surrender-percentage-to-take: 50.0

# 是否要开启加倍下注(可以加钱来提升下注金额，但是在抽了一张牌之后你就要拿走这个牌)
enable-double-down: true

# 这里你若开启了双倍下注，但是这个玩家没有足够的赌金来支付他们所亏欠的成本
# 那么玩家们会得到双倍赌资吗
# 假如，玩家A自己手头有100刀之后全部梭哈，同时加倍自己身上现有的赌资使其赌资变成200刀，但是玩家输了
# 输走了200刀，但是有很多经济插件没有余额为负这个功能，实际上最多只被扣除了100刀.
# 作者在此建议，将这个选项设置为关闭，除非你的经济插件内支持玩家让余额为负
double-down-overflow: false


# 是否禁用更改赌资选项（玩家改不了下注金额）
enable-change-bet: true

# 如果想要一个用户要求使用自定义指令那么就会在21点这个游戏开始之前执行指令
# 要使用这个选项，那么就将下面这条改成true 且自定义你想设置的指令
custom-command: false
command: "/Example $amount$"

# 希望21点里算上乘法吗(分数 of 21)?
enable-multiplier: true

# 关于21点的赌注里面要乘以多少
multiplier: 1.5


# 游戏内的向日葵图标是用来在菜单里增加/降低赌注数额的
bet-modifiers:
   increaseValue1: 10.0
   increaseValue2: 100.0
   increaseValue3: 1000.0
   decreaseValue1: 10.0
   decreaseValue2: 100.0
   decreaseValue3: 1000.0

# 插件内信息
number-or-player: "&c未知选项请使用/blackjack <amount> 或者 /blackjack <player>"
no-permission: "&c你没有任何权限使用这条指令"
menu-title: "21点: 多少赌注 $number$"
blackjack-dealer: "&8&l庄家"
blackjack-win: "&0&l你赢得了此次赌注&4&l这是你的赌金 &7&o($amount$x) "
dealer-lore: "&7&o拿走你的牌还是不拿?"
dealer-cards: "&e庄家的牌 ==>"
player-cards: "&e你的牌 ==>"
unknown-card: "&e???"
incorrect-args: "&c不正确的选项，麻烦请你使用 > /blackjack <amount> or /blackjack <player>"
hit-item: "&e拿牌"
stand-item: "&e停牌"
end-game: "&7玩家几点: &e$score$ &7庄家几点: &e$score2$"
earnings: "&e您得到了 $result$ $number$ 赌金!"
taxxed: "&c-$amount$ 税."
won: "赢了"
lost: "输了"
tied: "&e你只有赌赢了，才能拿回你的赌金"
cannot-bet-that-much: "&c你的钱并不能支撑你的赌金!"
can-only-bet: "&c你只能下注 $amount$ 且不能超过你自己本身的钱数!"
tutorial-name: "&e不知道怎么玩? 那么请点击一下这里"
tutorial:
  - "&e欢迎使用21点教程l! 若想退出, 请输入 &ccancel"
   - "&e21点这个游戏目标是，在你手里的牌不大于21点且小于21点，以你手上的牌来超越庄家手里的牌"
   - "&e 2-10这些卡牌等于卡面上的数字 (4 或者黑桃4)."
   - "&ejqk等于10 Ace 等于1或者11, 取决于出什么牌对玩家有利一些"
   - "&e'Hitting' 是发牌者给了你其余的牌，然后冒着输掉的风险，去拿发给你的牌"
   - "&e 'Standing' 是你认为自己的牌低于了21点，且大于庄家手里的牌，来结束这场游戏"
   - "&e谢谢你的游玩!"
bet-max-message: "&c最大下注 $amount$!"
bet-min-message: "&c最低下注 $amount$!"
surrender-item: "&e放弃下注"
surrender-lore: "&7&o(保留一半赌金)"
surrender-message: "&e你放弃了 $amount$ 原来的 $bet$ 赌金!"
double-down-item: "&e加倍"
double-down-lore: "&7&o(双倍下注，再发一张牌)"

# 会话信息
earnings-gui: "&e上一局游戏的收益:"
keep-playing: "&a还接着玩吗?"
stop-playing: "&c退出这一局?"
total-earnings: "&e全部收益: $amount$"
session-ending: "&e在 $amount$ 局游戏后, 你获得了 $$outcome$!"
change-bet-amount: "&e修改赌金金额"
your-bet-amount: "&e你的投注金额"
continue-playing: "接着继续玩, $player$?"

#新信息
blackjack: "&b21点"
previous-game: "&7正在加载上一局游戏. . ."
wins-stat: "&c赢了多少: &f$amount$"
loss-stat: "&c输了多少 &f$amount$"
ratio-stat: "&c输赢比率: &f$amount$"
amount-added: "&a+$amount$"
amount-subtracted: "&c-$amount$"


# 卡牌名
spades: "黑桃"
hearts: "红心"
clubs: "梅花"
diamonds: "方块"
jack: "Jack"
queen: "Queen"
king: "King"
ace: "王牌"
```

这些翻译还有选项可以根据你服务器的情况来修改
