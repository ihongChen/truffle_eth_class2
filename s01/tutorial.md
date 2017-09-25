## 乙太坊私有鍊啟用筆記(note)
由於Linux/Mac上 `geth.ipc`從錢包(Mist)會預設產生於根目錄`~/.ethereum`，必須另外指向原生`geth.ipc`資料夾。
1. 啟用私有鍊
    - 連結創世區塊 `genesis.json` 
    ```bash
    geth --datadir "./chaindata/" init gensis.json
    ```
    - 啟用私有鍊 
    ```bash 
    geth --datadir "./chaindata/" 
    ```
2. 啟用電子錢包(Mist)
    ``` bath 
    Ethereum\ Wallet --rpc ./chaindata/geth.ipc
    ```

3. 開啟`geth attach`
    ```
    geth attach ipc:./chaindata/geth.ipc # 進入geth cmd line
    miner.start(); # 挖礦
    ```