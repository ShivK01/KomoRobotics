# KomoRobotics
The Komo Robotics repository containing all the software for production, simulation, and test

### Docker Build Steps
One terminal -> `docker compose run --rm ros2_gazebo` or if if Dockerfile has changed -> `docker compose run --build --rm ros2_gazebo`\
Multiple terminals in same container -> `docker compose up -d` once then `docker compose exec ros2_gazebo bash` in each terminal