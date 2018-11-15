# Blockchain-web-apis

# Control blockchain by RESTful Web API

## Getting Started

Project uses Express.js Node framework. 

### Prerequisites

Things you need to know before using this app: Node.js and basics of Blockchain 


### Installing


```sh
# clone it
git clone 
cd project-folder

# Install dependencies
npm install

# Start development live-reload server
1) npm run dev 
or 
2) PORT=8080 npm run dev

# Start production server:
PORT=8080 npm start
```

Docker Support
------
```sh
cd express-es6-rest-api

# Build your docker
docker build -t blockchain/api-service .
#            ^      ^           ^
#          tag  tag name      Dockerfile location

# run your docker
docker run -p 8080:8080 blockchain/api-service
#                 ^            ^
#          bind the port    container tag
#          to your host
#          machine port   

```

## Built With

* [Node](https://nodejs.org/en/) - The web framework used

## Core APIS:

1) Get Block: The web API contains a GET endpoint that responds to a request using a URL path with a block height parameter or properly handles an error if the height parameter is out of bounds.

URL:  http://localhost:8000/block/1

```
GET Block example: when hitting http://localhost:8000/block/1

Response: 

{
"hash":"49cce61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acff3",
"height":0,
"body":"First block in the chain - Genesis block",
"time":"1530311457",
"previousBlockHash":""
}


```

2) Adding a block to Blockchain: The web API contains a POST endpoint that allows posting a new block with the data payload option to add data to the block body. Block body supports a string of text.


```
POST Block example:
URL: http://localhost:8000/block

Request:

{
      "body": "Testing block with test string data"
}

Response:

{
"hash":"49cce61ec3e6ae664514d5fa5722d86069cf981318fc303750ce66032d0acff3",
"height":0,
"body":"First block in the chain - Genesis block",
"time":"1530311457",
"previousBlockHash":""
}


```
 
3.Error Handler:  Service responds with appropriate error responses when posting or getting contents. 
A common error to watchout for - When posting to localhost:8000/block without any content on the payload, the service should not create a block. Be sure to validate if there is content in the block before creating and adding it to the chain.


## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Prit Sheth** 

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Boiler-plate from github.com:developit/express-es6-rest-api.git
* Udacity Blockchain Nanodegree
