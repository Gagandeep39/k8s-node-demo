# Steps to run

1. Create image nd push to docker hub
1. `kubectl create deployment k8s-node-demo-depl --image=k8s-node-demo`
2. Expoing to eternal world using service kubectl expose deployment k8s-node-demo-depl --port=8080 --type=NodePort
3. Scale `kubectl scale deployment/k8s-node-demo-depl --replicas=3`
4. Update
   1. Push Image ith new tag
   2. `kubectl set image deployment/k8s-node-demo-depl k8s-node-demo=gagandeep39/k8s-node-demo:1` (container_image_name=new_container_image_name)
5. Rollout status `kubectl rollout status deployment/k8s-node-demo-depl`
6. View Rollout history `kubectl rollout history deployment/k8s-node-demo-depl`
7. Rolbak to specific version `kubectl rollout undo deployment/k8s-node-demo-depl --to-revision=1`

## Steps to run - Declarative

1. Run `kubectl apply -f deployment.yml`
2. Delete `kubectl delete -f deployment.yml`
