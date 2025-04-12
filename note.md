##### https://github.com/kubernetes-sigs/kubespray/blob/master/docs/getting_started/setting-up-your-first-cluster.md

```bash
ku create deployment nginx --image=nginx
ku get po -w

ku run myshell1 -it --rm --image busybox -- sh
hostname -i

ku run myshell2 -it --rm --image busybox -- sh
ping myshell1_ip

ku create deployment nginx --image=nginx
ku port-forward nginx-5869d7778c-nz947 8080:80
curl 127.0.0.1:8080
ku -it exec nginx-5869d7778c-nz947 -- nginx -v
```

```bash
kubectl --config admin.conf get nodes
kubectl config get-contexts
kubectl config use-contexts k8s-cluster-01
kubectl config current-context
```
