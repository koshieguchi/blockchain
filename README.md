### Set up

In order to run this app, execute the following commands

```sh
$ python3 blockchain.py 5000
$ python3 blockchain.py 5001
```

### Basic Commands

```sh
# register the node
$ curl -X POST -H "Content-Type: application/json" -d '{
    "nodes": ["http://localhost:5001"]
}' "http://localhost:5000/nodes/register"

# mine blockchain
$ curl "http://localhost:5001/mine"

# add transactions
$ curl -X POST -H "Content-Type: application/json" -d '{
 "sender": "d4ee26eee15148ee92c6cd394edd974e",
 "recipient": "someone-other-address",
 "amount": 5
}' "http://localhost:5000/transactions/new"

# resolve conflicts among nodes
$ curl "http://localhost:5000/nodes/resolve"

# check the current node in the designated node
$ curl "http://localhost:5001/chain"
```
