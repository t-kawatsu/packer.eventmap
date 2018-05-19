interest with Ansible
=======================

自動構成管理ツールAnsibleを使用した
werewolfのサーバー構築/インストール

## Requirement

* ansible >= 1.9.4

## Usage

管理ノード(プロジェクトをインストールするサーバー)に  
developグループかつsudo出来るユーザを作成する
  
制御マシーンから本gitプロジェクトをcloneしソースディレクトリに移動  
  
※ まず実行する環境の環境設定ファイル( development or staging or production )内に記載されてある管理ノードのIPを確認/設定  

    git submodule update --recursive --force
  
サーバー構築実行

    ansible-playbook -i {development or staging or production} site.yml -u{管理ノードsshログインユーザー名}
  
(例

    ansible-playbook -idevelopment site.yml -uvagrant --ask-pass
  
※ 管理ノードのシステムFacts確認 (例

    ansible 192.168.33.10 -m setup -i development -uvagrant
  
  
>>完了後
  
### 管理ノード(WEBサーバー側)での作業  
  
プロジェクトのソースをcloneまたは直接sync  

    git clone ~~~

後のステップはwerewolf gitのREADMEを参照してください。  
<http://google.com>
