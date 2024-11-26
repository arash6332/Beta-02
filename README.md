cd $HOME
mkdir .sui
mv $HOME/sui/fullnode.yaml $HOME/.sui/
mv $HOME/.cargo/bin/sui-node /usr/local/bin/
2

echo "[Unit]
Description=Sui Node
After=network.target

mv $HOME/sui/fullnode.yaml $HOME/.sui/
User=$USER
Type=singgle
ExecStart=/usr/local/bin/sui-node --config-path $HOME/.sui/fullnode.yaml
Restart=on-failure
LimitNOFILE=65535

[Install]
WantedBy=multi-user.target" > $HOME/suid.service

3


4

sudo tee <<EOF >/
