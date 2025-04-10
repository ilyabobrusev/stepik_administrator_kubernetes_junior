```bash
## Установка k3s
curl -sfL https://get.k3s.io | INSTALL_K3S_EXEC="server --write-kubeconfig-mode 644" sh -

## Проверка
sudo k3s kubectl get nodes
sudo k3s kubectl get pods -A
sudo k3s kubectl get pods -A -w

## Донастройка 
export KUBECONFIG=~/.kube/config
mkdir ~/.kube 2> /dev/null
sudo k3s kubectl config view --raw > "$KUBECONFIG"
chmod 600 "$KUBECONFIG"

kubectl get pods -A

## На случай, если что-то пойдет не так
/usr/local/bin/k3s-uninstall.sh
```