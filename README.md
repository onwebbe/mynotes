<h1>Docker Mysql start</h1>
docker run -p 3306:3306 --name mymysql -v $PWD/conf:/etc/mysql/conf.d -v $PWD/logs:/logs -v $PWD/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.6

<h1>Node js config</h1>
npm install config --save<br/>
mkdir config<br/>
cd config<br/>
vi default.json<br/>
var config = require('config');<br/>
config.get('db.pwd');<br/>
