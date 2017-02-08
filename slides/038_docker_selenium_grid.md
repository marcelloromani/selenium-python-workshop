# Docker Selenium Grid
You can also use Docker to start a Selenium Grid hub and nodes. Each Docker container runs as a process on your host machine, so this isn't a way to massively scale, but it can be useful for supporting multiple browsers and running sessions in parallel.

# Exercise
1. Run a hub container: `docker run -d -p 4444:4444 --name selenium_hub selenium/hub`
2. Run three Firefox node containers: `docker run -d --link selenium_hub:hub selenium/node-firefox`
3. Run the tests against the Docker container by using the `Remote` driver and the appropriate value for `--port`
4. Open the web console at  http://localhost:4444/grid/console and see the nodes in use.
5. Kill the Docker containers: `docker kill [id]`
