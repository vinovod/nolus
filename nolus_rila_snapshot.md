Snapshot updates every 6 hours
Version tag: v0.1.43

How to use: 
```python

sudo systemctl stop nolusd

cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup

rm -rf $HOME/.nolus/data

curl -L http://ss1.nodessquad.com:9000/nolus-snap.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.nolus

mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json

sudo systemctl restart nolusd && sudo journalctl -u nolusd -f -o cat

```
