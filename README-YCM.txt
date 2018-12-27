This directory is only for code studying purpose. It is not runnable.
I add a lot of //comments in this project, which can not be found elsewhere.
Some modules may have comments with one space after //, these comments are added by developers not me.
TODO are the keyword i used to denote the areas that I want to take a detailed look in the future.
Some code need further explorations may be marked as //TODO: ??? or simply //???

=============

The actual running code is is managed by the active npm, which is in turn managed by nvm.
It can be found in ~/.nvm/... path

The 'node_modules' dir is copied from the /.nvm/... directory, which represent the installed/expanded copy of the same bitcore version.
All other files are directly unzipped from the bitcore github repository, which represent the unexpanded/original code.

As of 3 Nov 2pm, we have
yangchenming@Yangs-MacBook-Pro ~ $ cat ~/.bitcore/bitcore-node.json
{
  "version": "5.0.0-beta.44",
  "network": "testnet",
  "port": 3001,
  "services": [
    "address",
    "block",
    "db",
    "fee",
    "header",
    "mempool",
    "p2p",
    "timestamp",
    "transaction",
    "web",
    "insight-api",
    "insight-ui"
  ],
  "datadir": "/opt/bitcore5-data",
  "servicesConfig": {
    "p2p": {
      "peers": [
        { "ip": { "v4": "127.0.0.1" } }
      ]
    },
    "insight-api": {
      "routePrefix": "btc-api",
      "cwdRequirePath": "node_modules/insight-api"
    },
    "insight-ui": {
      "routePrefix": "btc",
      "apiPrefix": "btc-api",
      "cwdRequirePath": "node_modules/insight-ui"
    }
  }
}

As of 26 Oct 2pm, we have
[root@ap-explorer-import001 ~]# cat ~/.bitcore/bitcore-node.json
{
  "version": "5.0.0-beta.44",
  "network": "livenet",
  "port": 3001,
  "services": [
    "address",
    "block",
    "db",
    "fee",
    "header",
    "mempool",
    "p2p",
    "timestamp",
    "transaction",
    "web",
    "insight-api",
    "insight-ui"
  ],
  "datadir": "/opt/bitcoin-data",
  "servicesConfig": {
    "p2p": {
      "peers": [
        { "ip": { "v4": "127.0.0.1" } }
      ]
    },
    "insight-api": {
      "cwdRequirePath": "node_modules/insight-api"
    },
    "insight-ui": {
      "cwdRequirePath": "node_modules/insight-ui"
    }
  }
}


New Sample Output from log
===== bitcore-node/lib/cli/bitcored main start...
env.configPath and modulePath is not defined. taking the default setting
calling cli.daemon with parentServicesPath /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore additionalServices insight-api,insight-ui
===== bitcore-node/lib/cli/daemon main start...
program.config is not defined
[2018-11-03T08:55:54.580Z] info: scaffold/find-config.js starts
[2018-11-03T08:55:54.580Z] info: findConfig start searching from /Users/yangchenming/.bitcore dir by dir upwards till /root
configInfo is /Users/yangchenming/.bitcore [object Object]
servicesPath is /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore
start(configInfo)...
[2018-11-03T08:55:54.581Z] info: scaffold/start.js starts
[2018-11-03T08:55:54.582Z] info: effective servicesPath /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore
[2018-11-03T08:55:54.582Z] warn: setup services based on the config i.e. bitcore-node.json
[2018-11-03T08:55:54.582Z] info: process current working directory cwd is /Users/yangchenming/.bitcore
[2018-11-03T08:55:54.582Z] info: setup service address
[2018-11-03T08:55:54.582Z] info: setup service address its additional config is undefined
[2018-11-03T08:55:54.582Z] info: loading module for service address
[2018-11-03T08:55:54.582Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.582Z] info: - Checking the current working directory address for service: address
[2018-11-03T08:55:54.583Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: address
[2018-11-03T08:55:54.585Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.585Z] info: setup service block
[2018-11-03T08:55:54.585Z] info: setup service block its additional config is undefined
[2018-11-03T08:55:54.586Z] info: loading module for service block
[2018-11-03T08:55:54.586Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.586Z] info: - Checking the current working directory block for service: block
[2018-11-03T08:55:54.586Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: block
[2018-11-03T08:55:54.671Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.671Z] info: setup service db
[2018-11-03T08:55:54.671Z] info: setup service db its additional config is undefined
[2018-11-03T08:55:54.672Z] info: loading module for service db
[2018-11-03T08:55:54.672Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.672Z] info: - Checking the current working directory db for service: db
[2018-11-03T08:55:54.672Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: db
[2018-11-03T08:55:54.716Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.716Z] info: setup service fee
[2018-11-03T08:55:54.716Z] info: setup service fee its additional config is undefined
[2018-11-03T08:55:54.716Z] info: loading module for service fee
[2018-11-03T08:55:54.716Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.716Z] info: - Checking the current working directory fee for service: fee
[2018-11-03T08:55:54.717Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: fee
[2018-11-03T08:55:54.721Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.721Z] info: setup service header
[2018-11-03T08:55:54.721Z] info: setup service header its additional config is undefined
[2018-11-03T08:55:54.721Z] info: loading module for service header
[2018-11-03T08:55:54.721Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.721Z] info: - Checking the current working directory header for service: header
[2018-11-03T08:55:54.721Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: header
[2018-11-03T08:55:54.725Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.726Z] info: setup service mempool
[2018-11-03T08:55:54.726Z] info: setup service mempool its additional config is undefined
[2018-11-03T08:55:54.726Z] info: loading module for service mempool
[2018-11-03T08:55:54.726Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.726Z] info: - Checking the current working directory mempool for service: mempool
[2018-11-03T08:55:54.726Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: mempool
[2018-11-03T08:55:54.728Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.728Z] info: setup service p2p
[2018-11-03T08:55:54.728Z] info: setup service p2p its additional config is [object Object]
[2018-11-03T08:55:54.729Z] info: loading module for service p2p
[2018-11-03T08:55:54.729Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.729Z] info: - Checking the current working directory p2p for service: p2p
[2018-11-03T08:55:54.729Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: p2p
[2018-11-03T08:55:54.765Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.765Z] info: setup service timestamp
[2018-11-03T08:55:54.765Z] info: setup service timestamp its additional config is undefined
[2018-11-03T08:55:54.765Z] info: loading module for service timestamp
[2018-11-03T08:55:54.765Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.765Z] info: - Checking the current working directory timestamp for service: timestamp
[2018-11-03T08:55:54.765Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: timestamp
[2018-11-03T08:55:54.767Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.767Z] info: setup service transaction
[2018-11-03T08:55:54.767Z] info: setup service transaction its additional config is undefined
[2018-11-03T08:55:54.767Z] info: loading module for service transaction
[2018-11-03T08:55:54.767Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.767Z] info: - Checking the current working directory transaction for service: transaction
[2018-11-03T08:55:54.767Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: transaction
[2018-11-03T08:55:54.780Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.780Z] info: setup service web
[2018-11-03T08:55:54.780Z] info: setup service web its additional config is undefined
[2018-11-03T08:55:54.780Z] info: loading module for service web
[2018-11-03T08:55:54.780Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.780Z] info: - Checking the current working directory web for service: web
[2018-11-03T08:55:54.780Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: web
[2018-11-03T08:55:54.780Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:54.780Z] info: setup service insight-api
[2018-11-03T08:55:54.780Z] info: setup service insight-api its additional config is [object Object]
[2018-11-03T08:55:54.780Z] info: loading module for service insight-api
[2018-11-03T08:55:54.780Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:54.780Z] info: - Checking the current working directory node_modules/insight-api for service: insight-api
[2018-11-03T08:55:54.781Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: insight-api
[2018-11-03T08:55:54.781Z] info: - Checking the module's package.json for service: insight-api
[2018-11-03T08:55:55.358Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:55.358Z] info: setup service insight-ui
[2018-11-03T08:55:55.358Z] info: setup service insight-ui its additional config is [object Object]
[2018-11-03T08:55:55.358Z] info: loading module for service insight-ui
[2018-11-03T08:55:55.358Z] info: - Checking the service's requirePath for service: [object Object]
[2018-11-03T08:55:55.359Z] info: - Checking the current working directory node_modules/insight-ui for service: insight-ui
[2018-11-03T08:55:55.359Z] info: - Checking the built-in path: lib/services, ../services from /Users/yangchenming/.nvm/versions/node/v9.11.2/lib/node_modules/bitcore/node_modules/bitcore-node/lib/scaffold for service: insight-ui
[2018-11-03T08:55:55.359Z] info: - Checking the module's package.json for service: insight-ui
[2018-11-03T08:55:55.361Z] info: - found service code, setting service.module accordingly
[2018-11-03T08:55:55.361Z] warn: setupServices() ends
[2018-11-03T08:55:55.361Z] info: start.js instantiating a new instance of BitcoreNode
[2018-11-03T08:55:55.361Z] info: node.js _init() starts
[2018-11-03T08:55:55.361Z] info: start.js registering exit event handlers
[2018-11-03T08:55:55.362Z] info: node.js .start() starts
[2018-11-03T08:55:55.362Z] info: Using config: /Users/yangchenming/.bitcore/bitcore-node.json
[2018-11-03T08:55:55.362Z] info: Using network: testnet
[2018-11-03T08:55:55.363Z] info: ===== Starting db
[2018-11-03T08:55:55.386Z] info: ===== Starting timestamp
[2018-11-03T08:55:55.563Z] info: Db Service: service prefix for: timestamp is: 0001
[2018-11-03T08:55:55.564Z] info: ===== Starting p2p
[2018-11-03T08:55:55.583Z] info: p2p service peers defined, p2p _startBcoin() wont be called
[2018-11-03T08:55:55.584Z] info: ===== Starting header
[2018-11-03T08:55:55.585Z] info: Db Service: service prefix for: header is: 0002
[2018-11-03T08:55:55.585Z] info: db service getServiceTip about to get tip using utf8 encoded key: fffftip-header
[2018-11-03T08:55:55.586Z] info: db service getServiceTip keyBuf content is <Buffer ff ff 74 69 70 2d 68 65 61 64 65 72>
[2018-11-03T08:55:55.587Z] info: Getting last header synced at height: 1439781
[2018-11-03T08:55:55.666Z] info: ===== Starting mempool
[2018-11-03T08:55:55.667Z] info: Db Service: service prefix for: mempool is: 0003
[2018-11-03T08:55:55.667Z] info: Mempool Service: mempool disabled until full sync.
[2018-11-03T08:55:55.667Z] info: ===== Starting block
[2018-11-03T08:55:55.668Z] info: Db Service: service prefix for: block is: 0004
[2018-11-03T08:55:55.668Z] info: db service getServiceTip about to get tip using utf8 encoded key: fffftip-block
[2018-11-03T08:55:55.668Z] info: db service getServiceTip keyBuf content is <Buffer ff ff 74 69 70 2d 62 6c 6f 63 6b>
[2018-11-03T08:55:55.670Z] info: block service completed its sanity check on tip
[2018-11-03T08:55:55.671Z] info: utils.encodeTip about to encode in utf8: fffftip-block
[2018-11-03T08:55:55.671Z] info: block service about to _saveTip using key <Buffer ff ff 74 69 70 2d 62 6c 6f 63 6b>
[2018-11-03T08:55:55.828Z] info: Block Service: loaded: 144 hashes from the index.
[2018-11-03T08:55:55.828Z] info: ===== Starting transaction
[2018-11-03T08:55:55.828Z] info: Db Service: service prefix for: transaction is: 0005
[2018-11-03T08:55:55.828Z] info: ===== Starting address
[2018-11-03T08:55:55.829Z] info: Db Service: service prefix for: address is: 0006
[2018-11-03T08:55:55.829Z] info: ===== Starting fee
[2018-11-03T08:55:55.829Z] info: ===== Starting web
[2018-11-03T08:55:55.849Z] info: ===== Starting insight-api
[2018-11-03T08:55:55.851Z] info: localhost-insight-api subscribe: mempool/transaction total: 1
[2018-11-03T08:55:55.851Z] info: localhost-insight-api subscribe: block/block total: 1
[2018-11-03T08:55:55.851Z] info: ===== Starting insight-ui
[2018-11-03T08:56:05.789Z] info: start.js Bitcore Node ready
[2018-11-03T08:56:05.789Z] info: Connecting to p2p network.
[2018-11-03T08:56:05.867Z] info: printing : service name - effective routePrefix - effective apiPrefix
[2018-11-03T08:56:05.868Z] info: ==> db - db - undefined
[2018-11-03T08:56:05.868Z] info: ==> timestamp - timestamp - undefined
[2018-11-03T08:56:05.868Z] info: ==> p2p - p2p - undefined
[2018-11-03T08:56:05.868Z] info: ==> header - header - undefined
[2018-11-03T08:56:05.869Z] info: ==> mempool - mempool - undefined
[2018-11-03T08:56:05.869Z] info: ==> block - block - undefined
[2018-11-03T08:56:05.869Z] info: ==> transaction - transaction - undefined
[2018-11-03T08:56:05.869Z] info: ==> address - address - undefined
[2018-11-03T08:56:05.870Z] info: ==> fee - fee - undefined
[2018-11-03T08:56:05.870Z] info: ==> web - web - undefined
[2018-11-03T08:56:05.873Z] info: ==> insight-api - btc-api - undefined
[2018-11-03T08:56:05.874Z] info: ==> insight-ui - btc - btc-api
[2018-11-03T08:56:05.876Z] info: methodsMap - timestamp - getBlockHashesByTimestamp
[2018-11-03T08:56:05.876Z] info: methodsMap - p2p - clearInventoryCache
[2018-11-03T08:56:05.876Z] info: methodsMap - p2p - getP2PBlock
[2018-11-03T08:56:05.876Z] info: methodsMap - p2p - getHeaders
[2018-11-03T08:56:05.877Z] info: methodsMap - p2p - getMempool
[2018-11-03T08:56:05.877Z] info: methodsMap - p2p - sendTransaction
[2018-11-03T08:56:05.877Z] info: methodsMap - header - getAllHeaders
[2018-11-03T08:56:05.877Z] info: methodsMap - header - getBestHeight
[2018-11-03T08:56:05.877Z] info: methodsMap - header - getBlockHeader
[2018-11-03T08:56:05.877Z] info: methodsMap - mempool - getMempoolTransaction
[2018-11-03T08:56:05.877Z] info: methodsMap - mempool - getTxidsByAddress
[2018-11-03T08:56:05.877Z] info: methodsMap - block - getInfo
[2018-11-03T08:56:05.877Z] info: methodsMap - block - getBlock
[2018-11-03T08:56:05.877Z] info: methodsMap - block - getRawBlock
[2018-11-03T08:56:05.877Z] info: methodsMap - block - getBlockOverview
[2018-11-03T08:56:05.877Z] info: methodsMap - block - getBestBlockHash
[2018-11-03T08:56:05.897Z] info: methodsMap - block - syncPercentage
[2018-11-03T08:56:05.897Z] info: methodsMap - block - isSynced
[2018-11-03T08:56:05.898Z] info: methodsMap - transaction - getRawTransaction
[2018-11-03T08:56:05.898Z] info: methodsMap - transaction - getTransaction
[2018-11-03T08:56:05.898Z] info: methodsMap - transaction - getDetailedTransaction
[2018-11-03T08:56:05.898Z] info: methodsMap - transaction - setTxMetaInfo
[2018-11-03T08:56:05.898Z] info: methodsMap - address - getAddressHistory
[2018-11-03T08:56:05.898Z] info: methodsMap - address - getAddressSummary
[2018-11-03T08:56:05.898Z] info: methodsMap - address - getAddressUnspentOutputs
[2018-11-03T08:56:05.898Z] info: methodsMap - fee - estimateFee
[2018-11-03T08:56:05.902Z] info: Connected to peer: 127.0.0.1, network: testnet, version: 70015, subversion: /Satoshi:0.17.0/, status: ready, port: 18333, best height: 1441781
[2018-11-03T08:56:05.903Z] info: Header Service: Best Height is: 1441781
[2018-11-03T08:56:05.903Z] info: localhost-header unsubscribe: p2p/headers total: 0
[2018-11-03T08:56:05.903Z] info: localhost-header unsubscribe: p2p/block total: 0
[2018-11-03T08:56:05.904Z] info: Header Service: Gathering: 2000 header(s) from the peer-to-peer network.
[2018-11-03T08:56:05.904Z] info: Header Service: subscribed to p2p headers.
[2018-11-03T08:56:05.904Z] info: localhost-header subscribe: p2p/headers total: 1
[2018-11-03T08:56:06.091Z] info: utils.encodeTip about to encode in utf8: fffftip-header
[2018-11-03T08:56:06.113Z] info: Header Service: download progress: 1441781/1441781  (100.00%)
[2018-11-03T08:56:06.124Z] info: Header Service: p2p header subscription no longer needed, unsubscribing.
[2018-11-03T08:56:06.124Z] info: localhost-header unsubscribe: p2p/headers total: 0
[2018-11-03T08:56:06.124Z] info: Header Service: starting p2p block subscription.
[2018-11-03T08:56:06.124Z] info: localhost-header subscribe: p2p/block total: 1
[2018-11-03T08:56:06.124Z] info: Header Service: sync complete.
[2018-11-03T08:56:06.125Z] info: localhost-block unsubscribe: p2p/block total: 1
[2018-11-03T08:56:06.125Z] info: Block Service: checking the saved tip...
[2018-11-03T08:56:06.126Z] info: Block Service: saved tip is good to go.
[2018-11-03T08:56:06.126Z] info: Block Service: Gathering: 0 block(s) from the peer-to-peer network.
[2018-11-03T08:56:06.126Z] info: Block Service: download progress: 1441781/1441781  (100.0000%)
[2018-11-03T08:56:06.126Z] info: Block Service: starting p2p block subscription.
[2018-11-03T08:56:06.126Z] info: localhost-block subscribe: p2p/block total: 2
[2018-11-03T08:56:06.126Z] info: Mempool Service: Mempool enabled.
[2018-11-03T08:56:06.127Z] info: localhost-mempool subscribe: p2p/transaction total: 1
[2018-11-03T08:56:06.130Z] info: Block Service: The best block hash is: 0000000000000006575c299bd53e26dd52460294af1092b015ab4b356432defd at height: 1441781. Time between the last 2 blocks (adjusted): 2 minute(s). 44 second(s). 0 millisecond(s).
[2018-11-03T08:56:12.323Z] info: client with address ::1 web socket subscribe: inv
[2018-11-03T08:56:12.612Z] info: client with address ::1 web socket subscribe: sync
[2018-11-03T08:56:12.612Z] info: client with address ::1 web socket subscribe: sync
[2018-11-03T08:56:12.612Z] info: client with address ::1 web socket subscribe: sync
[2018-11-03T08:56:12.613Z] info: client with address ::1 web socket subscribe: sync

wait for another hours, a few more lines will get printed, indicating more blocks are mined on the p2p network
[2018-11-03T09:01:20.768Z] info: Block Service: The best block hash is: 00000000000000c4c5b631ac3714d5f5467d0f721930271d33d7eec64e19ecc7 at height: 1441782. Time between the last 2 blocks (adjusted): 7 minute(s). 57 second(s). 0 millisecond(s).

anytime when we visit the website, e.g. http://localhost:3001/btc, one line will get printed on console
[2018-11-03T09:01:20.818Z] info: ::1 "GET /btc-api/block/00000000000000c4c5b631ac3714d5f5467d0f721930271d33d7eec64e19ecc7" 200 - 38.762 "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36"
