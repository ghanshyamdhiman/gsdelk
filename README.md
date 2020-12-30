# gsdelk
alias python=python3
pip3 install vitualenv
python3 -m virtualenv ./gsdss/
source ./gsdss/bin/activate
git clone http://github.com/ghanshyamdhiman/gsdelk
pip3 install elasticsearch
cd ./gsdelk
git pull

python3 elk1.py

docker run --name elasticsearch -d -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" -v esdata:/usr/share/elasticsearch/data docker.elastic.co/elasticsearch/elasticsearch:6.3.2

docker run --name <some_name> --rm --link elasticsearch:elasticsearch --env ELASTICSEARCH_URL=http://elasticsearch:9200 <repo_name>

https://tryolabs.com/blog/2015/02/17/python-elasticsearch-first-steps/
