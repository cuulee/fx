fx
------

Poor man's function as a service.
<p>
  <img src="https://circleci.com/gh/metrue/fx.svg?style=svg&circle-token=bd62abac47802f8504faa4cf8db43e4f117e7cd7"/>
</p>

### Usage

* clone and build

make you have [dep](https://github.com/golang/dep) installed first.

```
$ git clone https://github.com/metrue/fx.git
$ cd fx
$ dep ensure
$ go install ./
```

* start server

```
fx serve
```

now you can make a function to service in a second.

```
fx up ./example/functions/func.js
```

the function defined in *exmaple/functions/func.js* is quite simple, it calculates the sum of two numbers then return;

func.js
```
module.exports = (input) => {
    return parseInt(input.a, 10) + parseInt(input.b, 10)
}
```

then you can test your service:

```
curl -X POST <service url> -H "Content-Type: application/json" -d '{"a": 1, "b": 1}'
```

of course you can do more.

```
Usage:
$ fx serve                                      start f(x) server
$ fx up   func1.js func2.py func3.go ...        deploy a function or a group of functions
$ fx down [service ID] ...                      destroy a function or a group of functions
$ fx list                                       list deployed services
$ fx --version                                  show current version of f(x)
```

### Features

* no API Gateway
* no Function Watchdog
* no Docker Swarm
* no Kubernets
* no fancy web dashboard

but f(x)

* **makes a function to be a service in seconds**.
* **supports all major programming languages (Node, Golang, Ruby, Python, PHP) functions to services**.


### Contributors

<table>
  <tbody>
    <tr>
      <td align="center" valign="top">
        <img width="150" height="150" src="https://github.com/metrue.png?s=150">
        <br>
        <a href="https://github.com/metrue">Minghe</a>
        <p>Core</p>
        <br>
        <p>Founder of f(x)</p>
      </td>
      <td align="center" valign="top">
        <img width="150" height="150" src="https://github.com/pplam.png?s=150">
        <br>
        <a href="https://github.com/pplam">Tim</a>
        <p>Core</p>
        <br>
        <p>Founder of f(x)</p>
      </td>
     </tr>
  </tbody>
</table>
