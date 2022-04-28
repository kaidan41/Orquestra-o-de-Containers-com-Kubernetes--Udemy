#Orquestração de conteiners com kubernetes comandos

#Verifciar historico de atualização deployments kubernetes
kubectl.exe rollout history deployment/nginx -n nomedonamespace

#Desfazer deployment
kubectl rollout undo deployment/nomedodeploy -n nomedonamespace

#Verificar o status do rollout
kubectl.exe rollout status deployment/frontend-dp -n frontend-namespace

#Gravar a saida do comando
kubectl.exe create -f Deployments/frontend-dp.yaml --save-config --record

#Setar a configuração direto pelo comando alterando a versão da imagem.
kubectl.exe set image deploy frontend-dp -n frontend-namespace frontend-container=nginx:1.18 --record

#DEsfazer a ultima atualização do deploy
kubectl.exe rollout undo deploy frontend-dp -n frontend-namespace

#Voltar versão específica do deployment no kubernetes
kubectl.exe rollout history deploy frontend-dp -n frontend-namespace

#Escalar o deploy da aplicação via comando
kubectl.exe scale deploy frontend-dp --replicas=10 -n frontend-namespace

