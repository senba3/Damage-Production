# Damage Production
 自分用のダメージ生成機

## Features
ダメージを指定することでそれっぽいダメージを作れるもの。プレイヤーや防具に対応！

## Usage /拡張一覧
damage: No.
　与えるダメージを100倍にして代入
　値が大きすぎると計算途中にスコアボードの限界値にぶつかってしまい､正常にダメージが通らない可能性があります
　マイクラの仕様がバグのせいで"体力1以下の操作ができないので"計算中に体力が1未満になるとkillされます
armor_rate: 0~100 [0]
　防具ダメージのカット割合｡0~100の範囲で設定出来ます
　0だとそのまま｡100だと防具が0.0倍(無効)に｡
effect_rate: 0~100 [0]
　耐性エフェクトのカット割合｡0~100の範囲で設定出来ます
　0だとそのまま｡100だと防具が0.0倍(無効)に｡
motion: 0b/1b/2b/3b [1b]
　ダメージモーションをとるかどうか｡0bでプレイヤーのみ､1bであり､2bでなし､3bでMOBのみ､
player_motion: 0b/1b [1b]
　死亡ログが出るかどうか
real_damage: 0b/1b [1b]
　対象を自動でMOBのみにし、エンドクリスタルは爆発します
hurt_particle: 0b/1b [0b]
　ダメージのパーティクルをだすかどうか｡1ダメージにつきハートが1個出ます
blood_particle: 0b/1b [0b]
　血のパーティクルをだすかどうか｡1ダメージにつき血が3滴出ます
kill: 0b/1b [1b]
　体力が0以下になったとき、殺すかどうか｡殺す代わりに対象に"senba.damage-killed"のタグを与えます｡エンドラとプレイヤー以外な
use_totem: 0b/1b/2b/3b [1b]
　死亡しそうになったら不死のトーテムを使うかどうか｡0bはトーテムを使わない｡2bと3bは､言葉で説明しにくいので割愛｡実際に使って変化を確かめてね｡私は1bが最適だと思いました｡
owner: []
攻撃元のownerをUUIDにて指定します。攻撃元のUUIDをどこかに保存しておいて､こちらのownerに貼り付けて下さい。
knockback: [1b]
"owner"が指定されたとき､0bにするとノックバックを受けなくなります。

※何も指定が無い場合や変なものが入ってるときは[ ]の中の結果になります
例:

## 例
=15ダメージを与える=

 /data merge storage senba.damage {damage:1500}

 /function senba.damage:main

=防具貫通50%でトーテムを使わせない10ダメージを与える=

 /data merge storage senba.damage {damage:1000,armor_rate:50,use_totem:0b}

 /function senba.damage:main

=付近のプレイヤーの攻撃で､5ダメージ与える=

 /data merge storage senba.damage {damage:500}

/data modify storage senba.damage owner set from entity @p UUID

# 仕様ライブラリ
https://ai-akaishi.booth.pm/items/3197831

