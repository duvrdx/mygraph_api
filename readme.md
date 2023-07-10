## /minPath

Endpoint para obter o menor caminho possível entre dois vértices.

### Requisição

`POST /minPath

#### Corpo da Requisição

```json
{
	"verticesNum": 3,
	"adjacencyMatrix":"0,12,2;12,0,5;2,5,0",
	"source":0,
	"destination":2
}
````

### Parâmetros de consulta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| verticesNum     | integer | Número de vértices presentes no grafo     |
| adjacencyMatrix  | string | Matriz de adjacencia (Celulas separadas por "," e linhas separadas por ";") |
| source  | integer | Vértice de saída  |
| destination  | integer | Vértice de chegada  |


### Resposta
Exemplo de resposta:
```json
{
	"statusCode": 200,
	"message": "OK",
	"data": [
		0,
		2
	]
}
```

### Parâmetros de resposta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| statusCode   | integer | Status da resposta     |
| message  | string | Descrição da resposta |
| data  | list(integer) | Lista com o menor caminho possível |

-----------------------------------------------------------------

## /allPaths

Endpoint para obter todos os caminhos possíveis a partir de um vértice.

### Requisição

`POST /allPaths`

#### Corpo da Requisição

```json
{
	"verticesNum": 3,
	"adjacencyMatrix":"0,12,2;12,0,5;2,5,0",
	"source":1
}
````

### Parâmetros de consulta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| verticesNum     | integer | Número de vértices presentes no grafo     |
| adjacencyMatrix  | string | Matriz de adjacencia (Celulas separadas por "," e linhas separadas por ";") |
| source  | integer | Vértice de saída  |


### Resposta
Exemplo de resposta:
```json
{
	"statusCode": 200,
	"message": "OK",
	"data": [
		1,
		0,
		2
	]
}
```

### Parâmetros de resposta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| statusCode   | integer | Status da resposta     |
| message  | string | Descrição da resposta |
| data  | list(integer) | Lista com busca em profundidade contendo os índices do grafo|

-----------------------------------------------------------------


## /maxFlow

Endpoint para obter o fluxo máximo de um grafo, a partir de uma saída e um destino.

### Requisição

`POST /maxFlow`

#### Corpo da Requisição

```json
{
	"verticesNum": 3,
	"adjacencyMatrix":"0,12,2;12,0,5;2,5,0",
	"source":1,
	"sink":2
}
````

### Parâmetros de consulta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| verticesNum     | integer | Número de vértices presentes no grafo     |
| adjacencyMatrix  | string | Matriz de adjacencia (Celulas separadas por "," e linhas separadas por ";") |
| source  | integer | Vértice de saída  |
| sink  | integer | Vértice de destino  |

### Resposta
Exemplo de resposta:
```json
{
	"statusCode": 200,
	"message": "OK",
	"data": 7.0
}
```

### Parâmetros de resposta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| statusCode   | integer | Status da resposta     |
| message  | string | Descrição da resposta |
| data  | float | Fluxo máximo  |

-----------------------------------------------------------------


## /neighbors

Endpoint para obter os vizinhos de um vértice no grafo.

### Requisição

`POST /neighbors`

#### Corpo da Requisição

```json
{
	"verticesNum": 3,
	"adjacencyMatrix":"0,12,2;12,0,5;2,5,0",
	"source":1,
}
````

### Parâmetros de consulta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| verticesNum     | integer | Número de vértices presentes no grafo     |
| adjacencyMatrix  | string | Matriz de adjacencia (Celulas separadas por "," e linhas separadas por ";") |
| source  | integer | Vértice de saída  |


### Resposta
Exemplo de resposta:
```json
{
	"statusCode": 200,
	"message": "OK",
	"data": {
		"0": 12.0,
		"2": 5.0
	}
}
```

### Parâmetros de resposta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| statusCode   | integer | Status da resposta     |
| message  | string | Descrição da resposta |
| data  | json | Conjunto chave-valor com índice do vizinho e peso da aresta  |

## /minimumSpamTree

Endpoint para obter a matriz de adjacencia da árvore geradora mínima de um grafo.

### Requisição

`POST /minimumSpamTree`

#### Corpo da Requisição

```json
{
	"verticesNum": 3,
	"adjacencyMatrix":"0,12,2;12,0,5;2,5,0",
	"source":1,
}
````

### Parâmetros de consulta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| verticesNum     | integer | Número de vértices presentes no grafo     |
| adjacencyMatrix  | string | Matriz de adjacencia (Celulas separadas por "," e linhas separadas por ";") |
| source  | integer | Vértice de saída  |


### Resposta
Exemplo de resposta:
```json
{
	"statusCode": 200,
	"message": "OK",
	"data": [
		[
			0.0,
			5.0,
			2.0
		],
		[
			5.0,
			0.0,
			0.0
		],
		[
			2.0,
			0.0,
			0.0
		]
	]
}
```

### Parâmetros de resposta

| Parâmetro  | Tipo   | Descrição           |
|------------|--------|---------------------|
| statusCode   | integer | Status da resposta     |
| message  | string | Descrição da resposta |
| data  | matrix | Matriz de adjacência da árvore geradora mínima  |


