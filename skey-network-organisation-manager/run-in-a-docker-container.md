# Run in a Docker container

### Development build <a href="#docs-internal-guid-fb267ef9-7fff-c7a7-1966-b114e65ee1f0" id="docs-internal-guid-fb267ef9-7fff-c7a7-1966-b114e65ee1f0"></a>

* install Docker
* clone the repository
* go to project folder
* run `cp .env.example .env.local`
* update ENV variables in `.env.local`
* run `docker build -f Dockerfile -t org-manager-dev .`
* run `docker run -d --name="org-manager-dev" org-manager-dev:latest`
* application will be available at port 3000

### Production build

* install Docker
* clone the repository
* go to project folder
* run `cp .env.example .env.local`
* update ENV variables in `.env.local`
* run `docker build -f Dockerfile.prod -t org-manager-prod .`
* run `docker run -d --name="org-manager" org-manager-prod:latest`
