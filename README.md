# docker-run-command v0.1.0

[![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org)
[![Github Issues](http://githubbadges.herokuapp.com/badges/badgerbadgerbadger/issues.svg?style=flat-square)](https://github.com/driesdroesbeke/docker-run-app/issues)
[![Pending Pull-Requests](http://githubbadges.herokuapp.com/badges/badgerbadgerbadger/pulls.svg?style=flat-square)](https://github.com/driesdroesbeke/docker-run-app/pulls)

The goal of this project is to make your live way easier when you want to use Docker to execute each cli command in a container instead of installing all packages (and versions) on your machine.

So if your are tired of passing way too many arguments to a docker run each time, you should take a look at the source code.

By default the script: 

* mounts the current folder into an /app folder in the container and sets the workdir
* mounts your ssh key / agent / socket / know_hosts so you can keep using your favorite package managers, connect to your servers or clone git projects
* sets the permission for files generated in the container to 777 since most containers run as root

## Usage

```
docker-run-app image command params
docker-run-app node:argon "npm test"
docker-run-app node:argon "node_modules/.bin/nodemon" "-p 4000:4000"
```

## Installing

You can copy/paste the file wherever you want or you can store it next to your other binaries.

```
sudo wget https://raw.githubusercontent.com/driesdroesbeke/docker-run-app/master/docker-run-app -O /usr/bin/docker-run-app
sudo chmod +x /usr/bin/docker-run-app
```

End with an example of getting some data out of the system or using it for a little demo

## Security

Since your ssh key is mounted you should only run containers you trust and in a controlled environment because all files generated in the /app folder will have 777 permissions on your host.

## Contributing

Feel free to create an issue. Pull requests are much appreciated.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

