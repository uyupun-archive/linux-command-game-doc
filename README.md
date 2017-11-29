:warning: CAUTION: ルールは予告なしに変更されることがあります.

# Linuxコマンドゲームとは
<img src="./logo.png" alt="Linuxコマンドゲーム" title="Linuxコマンドゲーム" width="300">

Linuxコマンドゲームとは, 様々なLinuxコマンドを駆使して戦う新しいカードゲームです.

ルールはいたってシンプルで, 先に自分の手札を０枚にした方が勝利です.

# 用語

|用語|説明|
|:--|:--|
|リポジトリ|山札のこと|
|ワークツリー|手札のこと|
|コミッター|プレイヤーのこと|
|コマンド|カードのこと|

# ルール
基本的に２人以上で行うゲームです.

コミッターはそれぞれリポジトリから５枚コマンドを引き, さっそくゲームスタートです.

コミッターは毎ターン１枚のコマンドをリポジトリから引き, ワークツリーに加えます.

その後, コミッターはワークツリーの中から任意のコマンドを１枚実行します(コマンドの実行は任意のためしなくても良い).

実行したコマンドに応じた処理を行い, 自分のターンを終了とします.

この一連の流れを繰り返し, 先に自分のワークツリーを０枚にしたコミッターが勝利です.

# コマンド一覧

|コマンド名|処理|
|:--|:--|
|cat|相手コミッターは１ターンの間, ワークツリーを開示する.|
|ls|お互いのコミッターは１ターンの間, ワークツリーを開示する.|
|cp|自分のワークツリーにある任意の１枚のコマンドと同名のコマンドをリポジトリからワークツリーに加える.|
|find|リポジトリから任意のコマンドを自分のワークツリーに加える.|
|mv|① ワークツリーにある任意の１枚のコマンドを相手コミッターのワークツリー又はリポジトリに移動する.<br>② ワークツリーにある任意の１枚のコマンドを相手コミッターのワークツリー又はリポジトリの任意の１枚のコマンドと交換する.|
|touch|自分又は相手コミッターはリポジトリから１枚引き, ワークツリーに加える.|
|rm|自分又は相手コミッターのワークツリーから１枚選択し, リポジトリに戻す.|
|mkdir|自分又は相手コミッターはリポジトリから３枚まで引き, ワークツリーに加える.|
|rmdir|自分又は相手コミッターのワークツリーから３枚まで選択し, リポジトリに戻す.|
|sudo|自分又は相手コミッターに対して任意のコマンドを実行できる.<br>ただし, fork bombは実行できない.|
|fork bomb|相手コミッターのワークツリーの枚数分リポジトリからワークツリーに加える.<br>fork bombはドロー以外でワークツリーに加えることはできない.<br>また, 実行後はゲームから除外される(リポジトリに戻らない).|
|↑|前回実行したコマンドを再度実行する.<br>ただし, fork bombは実行できない.|
|command + c|相手が実行したコマンドを無効化する.<br>このコマンドはこのゲームの中で唯一相手ターン中に実行できるコマンドである.|
|-f|このオプションをつけて実行されたコマンドはcommand + cで無効化されることはない.<br>ただし, 次のターンはコマンドを実行できない.|
|-r|このオプションをつけてコマンドを実行した場合, 同名のコマンドを４回まで続けて実行することができる<br>ただし, 同名のコマンドがワークツリーにない場合は実行できない.<br>また, 次のターンはコマンドを実行できない.|

# カード枚数
fork bomb, mkdir, rmdir, オプションはそれぞれ２枚ずつ, その他のコマンドは４枚ずつの計50枚から構成される.
