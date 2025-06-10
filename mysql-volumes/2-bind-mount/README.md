# Volume Bind Mount

Esse é o segundo conceito prático sobre volumes. Aqui, vou mapeiar os dados para uma pasta local. Isso te ajuda a ver os arquivos reais que o MySQL cria.

```bash
mkdir -p $(pwd)/docker/mysql-data
```
```bash
docker run -d \
  --name mysql-bind \
  -e MYSQL_ROOT_PASSWORD=senha123 \
  -v $(pwd)/docker/mysql-data:/var/lib/mysql \
  -p 3306:3306 \
  mysql:8.0
```

Verifique com:

```bash
ls $(pwd)/docker/mysql-data
```