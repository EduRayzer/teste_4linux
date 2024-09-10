# teste_4linux
Etapa 1

Na primeira etapa eu fiz criacao dos cluster localmente na minha maquina.

-Instalacao do Ansible(sudo apt update && sudo apt install ansible -y)
-Criacao do arquivo hosts.ini onde defini os grupos host de master e workers e adicionei as variaveis.
localmente a variavel"ansible_ssh_private_key_file" eu puis o caminho da minha chave localmente.
-Criacao do playbook do ansible "install_k3s.yml" onde defini que o grupo master vai executar priveligio root, "curl -sfL https://get.k3s.io | sh -" a instalacao k3s diretamente no no master.
Registrar o token no caminho indicado. E a instalacao do k3s no grupo workers, e a execucao do playbook Ansible com um arquivo de inventário específico
O mesmo cluster pode ser verificador na Vm que foram instalados com sucesso.

Tentei criar uma pipeline "ansible-setup.yml" para que a primeira etpada rodasse por pipe mas estava dando problema na parte de leitura da chave ssh.

Etapa 2

-Criacao do pipeline e do arquivo deployment.yaml
-No "deployment.yaml" cria e gerencia 3 replicas da aplicação coffee-shop usando a imagem. Cria um serviço do tipo LoadBalancer, para a porta 80.
-Criacao do arquivo "deploy.yaml" para rodar toda vez que tiver alguma atualizacao no githubactions. Constrói a imagem Docker da aplicação coffee-shop em cada commit no branch main.
Implanta a aplicação em um cluster Kubernetes (K3s) após a construção bem-sucedida,utilizando os secrets do GitHub para garantir a segurança das credenciais de acesso ao cluster.

Etapa nao concluida.

Resumo: O mesmo tive dificuldades por terminar por certas coisas ser novas para mim. Somente a etapa 1 consegui concluir e tentei a Etapa 2, a etapa 3 nao cheguei iniciar, por falta de tempo nao consegui continuar.
Recomendacoes futuras: Fazer testes de implementacao de aplicacao com o que o proprio executante tenha criado.
