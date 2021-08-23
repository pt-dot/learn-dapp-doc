# Development SC(Smart Contract)
Development untuk smarcontract bisa menggunakan framework `truffle`. Truffle sudah tersetup untuk proses testing maupun migrasi.

# Local ethereum client 
Truffle sudah satu bundle dengan tool `ganache`. Ganache dipakai untuk ethereum client secara local, nantinya transaksi dari SC akan dieksekusi secara local di ganache.

# Ethereum Network
terdapat beberapa ethereum network seperti `main net`, `rinkeby`, `ropsten`, etc.
`main net` digunakan untuk production network sedangkan `rinkeby` dan `ropsten` digunakan untuk development mode dan masih terdapat beberapa network lainnya.

# Live IDE 
Remix adalah ide online yang bisa digunkan untuk melakukan development SC. Penggunaan remix lebih baik digunakan untuk mencoba/test suatu SC, untuk development secara lengkapnya bisa dilakukan di truffle.

# Verify SC
untuk melakukan verify SC terdapat beberapa cara. Cara yang biasa digunakan dan support dengan truffle adalah package npm `truffle-plugin-verify`. Proses verifikasi menggunakan package ini lebih mudah.

## Verify Binaries yang sama
Jika terdapat beberapa SC yang memiliki binaries yang sama, dan terdapat salah satu yang sudah terverifikasi, maka SC lain yang memiliki binaries yang sama ikut terverifikasi. Di etherscan akan terdeteksi bahwa SC tersebut memiliki kesamaan binaries dengan SC lain.

### Proses verifikasi signature
https://solidity-by-example.org/signature/