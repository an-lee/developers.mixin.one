# Node.js SDK

### Installation
```shell
npm install mixin-node-sdk --save
```

### Example
```js
const { Mixin } = require('mixin-node-sdk')
const CLIENT_CONFIG = {
    client_id: '',
    client_secret: '',
    pin: '',
    session_id: '',
    pin_token: '',
    private_key: ``
}

// 1. The first parameter is the information of the keystore
// 2. The second parameter is whether to use Chinese domain name acceleration. It is recommended that Chinese servers fill in true.
// 3. The third parameter is whether to enable debug mode, and some log information will be displayed on the console.
const client = new Mixin(CLIENT_CONFIG, true, true)

const user = client.create_user({
    full_name: 'test',
    session_secret: `MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQC8wF10XuA2i90YC1peIY4ZzL0N
        pdbXw8uNakCIjMnBeAGGHFvBFgU11uf1asP/8rtLLZfiNwwFlrayErT6SyDB27qv
        POb/vaS4X6mfz9qA0nEz4pHvoTnNV0/L+VftHA43uq46VObDejKJp2wuniY1AT22
        D+NWTjvp/IZ0FvMVqwIDAQAB`
})
console.log(user)

// replace PIN
client.pin_update({
    old_pin: '918869',
    pin: '918869'
})

// View details of the asset in the account
const assets = client.query_assets({
    asset_id
})
console.log(assets)
```

---
This SDK is developed by the Mixin team. If you have any questions, you can search for 30265 through Mixin Messenger and contact us for help.