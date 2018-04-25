# Daemon
```bash
docker run --name IntensecoinDaemon --volume daemon:/daemon/data easyhash/intensecoin:latest /daemon/intensecoind --log-level=0 --rpc-bind-ip=0.0.0.0 --rpc-bind-port=18081 --data-dir=/daemon/data --hide-my-port --confirm-external-bind --add-exclusive-node 140.82.9.90:48772 --add-exclusive-node 62.48.164.60:48772 --add-exclusive-node 5.249.27.162:48772
```

# Wallet
```bash
docker run --name IntensecoinWallet --volume wallet:/daemon/data --link IntensecoinDaemon:daemon easyhash/intensecoin:latest /daemon/intense-wallet-rpc --daemon-address=http://daemon:18081 --wallet-file=/daemon/data/intensecoin.wallet --rpc-bind-ip=0.0.0.0 --rpc-bind-port=18082 --password '<wallet password>' --confirm-external-bind --trusted-daemon --disable-rpc-login
```