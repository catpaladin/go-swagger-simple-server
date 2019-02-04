# Go Swagger Simple Server

project made through [this](https://goswagger.io/)

## validate

```swagger
swagger validate swagger.yml
```

## generate server

```swagger
swagger generate server -A todo-list -f ./swagger.yml
```

## run server

```go
go run cmd/todo-list-server/main.go
```

## test the server

test availability
```bash
curl -i localhost:<port>
```

create item
```bash
curl -i localhost:<port> -d "{\"description\":\"message $RANDOM\"}"
```

create item with `Content-Type`
```bash
curl -i localhost:<port> -d "{\"description\":\"message $RANDOM\"}" -H 'Content-Type: application/io.goswagger.examples.todo-list.v1+json'
```

update description for `id: 3`
```bash
curl -i localhost:<port>/3 -X PUT -H 'Content-Type: application/io.goswagger.examples.todo-list.v1+json' -d '{"description":"eat bananas"}'
```

delete item with `id: 1`
```bash
curl -i localhost:<port>/1 -X DELETE -H 'Content-Type: application/io.goswagger.examples.todo-list.v1+json'
```