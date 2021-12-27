### Run binance announcement site scraper
nohup python3 -u ./manager.py -E scraper -e binance -t scraper > binance.log &

### Run binance announcement api
nohup python3 -u ./manager.py -E scraper -e binance -t api > api_binance.log &

### Run coinbase medium announcement scraper
nohup python3 -u ./manager.py -E scraper -e coinbase -t scraper > coinbase.log &

### Run coinbase api diff script scraper
nohup python3 -u ./manager.py -E scraper -e coinbase -t api > api_coinbase.log &


### Update order status Binance
nohup python3 -u ./manager.py -E order-status -e binance

### Update order status Gate.io
nohup python3 -u ./manager.py -E order-status -e gateio


### Create database
```
$psql -U postgres
#CREATE DATABASE DB_NAME;
```

### Set database password
```
#ALTER USER postgres PASSWORD 'DB_PASSWORD';
```

### Clone
```
git clone https://gitlab.com/a3557/info-arbitrage
cd info-arbitrage
```

### Create virtual environment
```
python3 -m venv env
source env/bin/activate
pip3 install -r requirements.txt
alembic upgrade head
```


