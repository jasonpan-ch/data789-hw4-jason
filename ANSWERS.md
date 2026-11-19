# HW4 — Short Answers

Answer each question in 2–3 sentences.

## 1. Rolling-update safety
Why does the Deployment use `maxUnavailable: 0`, and what would change if it were `maxUnavailable: 1`?

> Deployment uses maxUnavilable: 0 since it ensures that there would be no unavilable pod during the rolling updates. If it were to be changed to 1, then Kubernetes would allow one pod to be off which means that the other two pods in the system would to pick up the load. This may cause higher latency or failures if the entire system is under load.

## 2. Health probes
Why do the liveness/readiness probes target `/health` instead of `/predict`?

> The liveness/readiness uses /health instead of /predict since health check whether the application is responding and predict actually performes the fraud detection. Health is faster and simpler in checking the status when a prediction isn't needed.

## 3. Autoscaling under load
Your HPA scales at 40% CPU up to 8 pods. If request volume doubled, what would you expect to happen — and what happens once it reaches the maximum?

> If the request volume doubled, I expect that Kubernetes would open up more pods in order to distribute the load. Once the CPU is at 100%, all 8 pods are up and it cannot open up anymore.
