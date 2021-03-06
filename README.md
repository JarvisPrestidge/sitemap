# Domain Crawler

Simple command line program to crawl a single domain implemented in Go.

# Usage

The program takes a single argument - a url with which to crawl.

Example: 

```bash
$ sitemap http://golangweekly.com
```

and outputs the scraped URLs to a *.sitemap file in an `output` directory created from where the command is ran.


# How to run

* ## Install Go


If you have Go installed on your machine (with the correct GOPATH and GOROOT environment variables set) and the recommended Go workspace structure set up. Then it's as easy as cloning the repo, for example:

```bash
$ git clone https://github.com/jarvisprestidge/sitemap.git
```

Then `cd` into the repo and now you have a couple of options to run the program.

 ***Go Install***
 
 You can install the binary into your `$GOPATH/bin` folder running the following in the root of the package:
 
```bash
$ go install
```

The `sitemap` binary can then be found in the workspaces `/bin` folder (or available anywhere if you've added this location to you path).

```bash
$ sitemap <url to scrape>
```

 ***Go Run***
 
 To lauch the program ad-hoc and have the Go compiler build and run the binary in one step you can use the `go run` option, for example:
 
```bash
$ go run sitemap.go <url to scrape>
```

> The `sitemap` binary can then be found in the workspaces' bin folder (or available anywhere if you've added this location to your path).

* ## Build Docker container (dockerfile)

Have a working version of docker running installed.

Clone the repo to a directory of your chosing and cd into that repo. Build the docker image from the dockerfile in the root of the repo using the following command in the terminal:

```bash
$ docker build -t <inset image name> .
```

From here, simply run the newly created image using the following:

```bash
$ docker run -it <name of image>
```

This will spin up the container and place you in a shell inside the `go/github.com/jarvisprestidge/sitemap` directory. Then run the program with either of the options detailed above in *How to run*.


# Running Tests

* #### [Ginkgo](https://onsi.github.io/ginkgo/) - [Github](https://github.com/onsi/ginkgo) - BDD testing framework

* #### [Gomega](https://onsi.github.io/gomega/) - [Github](https://github.com/onsi/gomega) - Assertion library

Ensure you have both the testing framework (Ginkgo) and the assertion library (Gomega) are installed by running the following:

```bash
$ go get github.com/onsi/ginkgo/ginkgo
$ go get github.com/onsi/gomega
```

Then when in the root directory of the package, execute the tests with either:

`go test` or `ginkgo`

> Running `ginkgo -v` will output the specs as well.


