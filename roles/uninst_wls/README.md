
## Install 編

### 実行コマンドライン例

```bash
java -jar fmw_12.2.1.2.0_wls_generic.jar -silent -responseFile /home/exampleuser/response/wls.rsp
```
#### oraInst.loc ファイルが必要な件

```bash
/tmp/OraInstall2016-11-02_11-42-31AMからOracle Universal Installerの起動を準備中
ファイル{0}を読み取れません。
oraInstFile: /etc/oraInst.loc


このホストで最初のインストールを開始しているか、現在のインベントリにアクセスするための十分な権限がありません。このインストールの一部として、インストーラ・ファイルのディレクトリを指定する必要があります。これは"インベントリ・ディレクトリ"と呼ばれます。インベントリ・ディレクトリ内には、インストーラによりインベントリ・データを格納する各製品のサブディレクトリが自動的に作成されます。通常、1製品当たり150KBが消費されます。
このファイル(oraInst.loc)は、/etcディレクトリに作成することをお薦めします。これを行うにはroot権限が必要です。インストーラを終了し、/tmp/createCentralInventory1478054557118.shにあるスクリプトを実行して、中央インベントリの場所を設定できます。

中央インベントリの場所ポインタ・ファイル(/etc/oraInst.loc)を作成せずにインストールを続行する場合は、任意の書込み可能な場所に
inventory_loc=<inventory_location>
inst_group=<group_name>
というコンテンツを含むファイルを作成し、-invPtrLocフラグ付きでインストーラを実行できます。

例 java -jar <installer file> -silent -respFile <response file location> -invPtrLoc <absolute path to the file>
```

### 以下の感じでファイル作って

######  oraInst.loc

```bash
inventory_loc=$HOME/oraInventory
inst_group=weblogic
```

```bash
java -jar <installer file> -silent -respFile <response file location> -invPtrLoc {PATH}/oraInst.loc
```


## Uninstall 編

```bash
/opt/ofm/wls/12211/oui/bin/deinstall.sh -silent -responseFile /home/weblogic/wls12212-full-deinst.rsp -logLevel FINE
```


###### 参考 URL

- [2 Using the Oracle Universal Installer in Silent Mode](https://docs.oracle.com/middleware/12212/lcm/OUIRF/GUID-2DBCEBB2-165B-4976-A3B8-9B25C30BAC2B.htm#OUIRF323)
- [C Sample Response Files for Silent Installation and Deinstallation](https://docs.oracle.com/middleware/12212/lcm/OUIRF/GUID-19DEEA75-CC63-47D4-BDC7-038E133490E0.htm#OUIRF370)


