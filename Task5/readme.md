Создать поды:

kubectl run front-end-app --image=nginx --labels role=front-end --expose --port 80

kubectl run back-end-app --image=nginx --labels role=back-end-api --expose --port 80 

kubectl run admin-back-end-app --image=nginx --labels role=admin-back-end-api --expose --port 80

kubectl run admin-front-end-app --image=nginx --labels role=admin-front-end --expose --port 80    



```bash

# Применить политики из файла
kubectl apply -f .\Task5\networks.yaml

#Проверка работы сети 
    
# Frontend → Backend (должно работать) ✅
kubectl exec front-end-app -- curl -s --connect-timeout 2 http://back-end-app

# Admin Frontend → Admin Backend (должно работать) ✅
kubectl exec admin-front-end-app -- curl -s --connect-timeout 2 http://admin-back-end-app

# Frontend → Admin Backend (должно НЕ работать) ✅
kubectl exec front-end-app -- curl -s --connect-timeout 2 http://admin-back-end-app 

# Admin Frontend → Backend (должно НЕ работать) ✅
kubectl exec admin-front-end-app -- curl -s --connect-timeout 2 http://back-end-app