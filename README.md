### Create virtual environment
```
cd info-arbitrage
python3 -m venv env
source env/bin/activate
pip3 install -r requirements.txt
```

### Create database
```
$psql -U postgres
#CREATE DATABASE DB_NAME;
```

### Set database password
```
#ALTER USER postgres PASSWORD 'DB_PASSWORD';
```
### migration
```
alembic upgrade head
```

### Run binance announcement site scraper
nohup python3 -u ./manager.py -E scraper -e binance -t scraper > binance.log &

### Run binance announcement api
nohup python3 -u ./manager.py -E scraper -e binance -t api > api_binance.log &

### Run coinbase medium announcement scraper
nohup python3 -u ./manager.py -E scraper -e coinbase -t scraper > coinbase.log &

### Run coinbase api diff script scraper
nohup python3 -u ./manager.py -E scraper -e coinbase -t api > api_coinbase.log &
