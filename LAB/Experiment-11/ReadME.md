## Step 7: Stop Application

Command:

```
docker compose down
```
![3](./images/3.png)
Result:

- Containers removed
- Network removed
- Volumes remain intact

---

# Scaling Experiment

## Scaling WordPress Service

Command:

```
docker compose up --scale wordpress=3
```
![7](./images/7.png)
Observation:

Error due to fixed container name.

Error reason:

Docker requires unique container names for scaling.

Solution:

Remove:

```
container_name: wordpress_app
```

Then scaling works correctly.

---

# Docker Swarm Deployment

## Step 1: Initialize Swarm

Command:

```
docker swarm init
```
![8](./images/8.png)

Observation:

Node initialized as manager.

---

## Step 2: Deploy Stack

Command:

```
docker stack deploy -c docker-compose.yml wpstack
```
![5](./images/5.png)
Observation:

Services created:

```
wpstack_db
wpstack_wordpress
wpstack_nginx
```

---

## Step 3: Verify Services

Command:

```
docker service ls
```
![9](./images/9.png)
Observed services:

```
wpstack_db
wpstack_nginx
wpstack_wordpress
```

---

## Step 4: Scale Service

Command:

```
docker service scale wpstack_wordpress=3
```
![10](./images/10.png)
Observation:

```
overall progress: 3 out of 3 tasks
verify: Service converged
```

---

## Step 5: Verify Replicas

Command:

```
docker service ps wpstack_wordpress
```
![11](./images/11.png)
Observation:

Three WordPress containers running successfully.

---
