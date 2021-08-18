## ERC 20 Transaction
dibeberapa transaksi ada yang menggunakan token ERC20, misal transaksi menggunakan WETH, USDT, USDC.<br>

Jika transaksi pada suatu kontrak melakukan proses transfer token ERC 20 terlebih dahulu user melakukan approval untuk memberikan izin smart contract untuk melakukan transaksi menggunakan token ERC 20 yang dimiliki user.
sample code ketika melakukan `approve`

```
 const approveMethod = usdcContract.methods.approve(
      partyAddress,
      web3.utils.toWei(new BN(config.approveAmount), 'mwei')
    ) as ContractSendMethod;
    return approveMethod.send({ from: account });
  };
```

func approve ini dimiliki oleh contract USDC akan melakukan set allowance terhadap wallet user, sehingga Contract USDC bisa melakukan transaksi terhadap wallet user


### contoh kasus:
User ingin melakukan topup ke sebuah SC. SC tersebut memiliki function deposit.
wallet yang diterima oleh SC adalah USDC. Jika user melakukan transfer secara langsung kepada SC maka tidak diperlukan set allowance karena yang melakukan transfer adalah user sendiri, tetapi berbeda ketika proses transfer dilakukan oleh SC. Semisal proses transfer hanya bisa dilakukan dengan kondisi kondisi tertentu, maka di SC tersebut menyediakan func deposit yang sudah memiliki kondisi yang dibutuhkan, jika kondisi terpenuhi maka SC akan mengambil sejumlah token dari user, maka pada kasus ini perlu dilakukan set allowance dengan memanggil func `approve`.