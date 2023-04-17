# <a name=“instru”><a/> Desafio Git/Github DIO - Instruções básicas

### Instruções iniciais para configurar uma chave ssh para conexão segura local no github e um passo a passo para criar um repositório no github e na máquina local.
É possível utilizar vários sistemas operacionais para realizar estes processos, cada um pode ter suas particularidades, o sistemas utilizado foi o Linux e o GitHub estava com a Interface na linguagem Inglês, por isso alguns termos não estão em português e o CLI (Comand Line Interface) é citado várias vezes, ao invés de outro sistema que podem ser usado no Windows por exemplo. Mas no geral não há muita diferenciação nesses passos iniciais, por isso dá para seguir normalmente e qualquer detalhe mais específico pode consultar vídeos de utilização no Windows ou em aparelhos da Apple.

#### 1. Criar uma conta no Github.
#### 2. Ter conhecimento básico de linha de comando, por exemplo, saber sobre os comandos ls, cd, mkdir.
#### 3. Verificar qual o sistema operacional e em seguida instalar o [Git](https://git-scm.com/) localmente.
#### 4. Criar [chave ssh](#chave-ssh) para conexão segura e automática para conexão entre repositório local e o GitHub.
#### 5. Agora que possui uma conexão segura é preciso testar alguns passos para versionamento do que é produzido.
#### 6. Primeiro [cria um reposítório no GitHub e clona na máquina local](#cria_clona_rep). 
#### 7. Para teste, cria um arquivo de texto e insere algo, salva o arquivo teste.txt na pasta que foi clonada do GitHub
#### 8. Será utilizado alguns comando do Git.
#### 9. No CLI acessa a pasta que o arquivo está e digita <git status>, vai verificar algumas informações sobre o processo git local.
#### 10. Digita <git add .> para adicionar o novo arquivo no controle de versão local.
#### 11. Em seguida é recomendável adicionar um comentário a edição feita.
#### 12. Digita o comando <git commit -m "Comentário referente ao arquivo inserido/atualizado">, este comando cria um commit local.
#### 13. Para adicionar as edições locais na nuvem, neste caso no GitHub, digita <git push origin main> + enter, vai ser solicitada a senha da chave ssh.
#### 14. Agora que adicionou só verificar no GitHub se o arquivo já aparece.
#### 15. Por fim, caso faça uma alteração e ela esteja na nuvem e precise puxar para a máquina local, é só digitar o comando <git pull>


## Chave SSH

#### 1. Gera uma chave na linha de comando da máquina localmente, via CLI, e conecta com a respectiva parte no GitHub.
#### 2. Para gerar a chave digita no CLI o seguinte comando, sem os sinais menor/maior, <ssh-keygen -t ed25519 -C seu_email> 
#### 3. Onde tem seu_email coloca o email conectado no github, em seguida pode apertar enter e prosseguir
#### 4. Pode apertar enter novamente ou inserir o diretório que deseja salvar a chave ssh e aperta enter.
#### 5. É solicitada uma senha para proteção do arquivo da chave, insere e aperta enter novamente.
#### 6. Pela linha de comando (CLI) vai se direcionar para o local em que a chave foi salva e digitar o seguinte <cd .ssh> + enter
#### 7. Em seguida <ls> + enter, e <cat id_ed25519.pub> + enter, copia a chave que apareceu e [adiciona no GitHub](#add_github).


## Adicionar chave no GitHub{#add_github}
Importante destacar que a chave é para não precisar ficar conectando manualmente toda vez que vai realizar alguma ação que tenha por objetibo conectar o github e a máquina em que está usando. Pode gerar tokens com tempo determinado de conexão, mas é outro processo, para mais informações pode verificar na [documentação do github](https://docs.github.com/pt).

#### 1. Acessa a conta no GitHub
#### 2. Clica no perfil e vai em settings.
#### 3. Em seguida clica em 'SSH and GPG keys'. 
#### 4. CLica em 'new SSH key'.
#### 5. Adiciona um título (title) para a chave.
#### 6. Escolhe o tipo da chave (Key Type) e cola a chave que foi copiada no passo 7 da configuração da chave SSH.
#### 7. Para conectar de forma segura é só digitar os seguintes comandos no CLI.
#### 8. /<eval $(ssh-agent -s)> + enter
#### 9. /<ls> + enter
#### 10. /<ssh-add id_ed25519> + enter

Voltar para as [Instruções básicas](#instru).

## Criar e clonar um repositório do GitHub {#cria_clona_rep}

#### 1. Acessa o GitHub, vai no perfil e clica em setting "Your repositories".
#### 2. Clica em New, vai abrir outra página, insere o nome do repositório (Repository name).
#### 3. Insere uma descrição, é opcional.
#### 4. Define se será público ou privado (public or private), de acordo com as necessidades do seu projeto.
#### 5. É recomendável adicionar o README file, se quiser só marcar a opção para adicionar ele.
#### 6. Pode clicar em "Create repository", caso precise de mais algumas informações só acessar a [Documentação do github](https://docs.github.com/pt).
#### 7. Agora é preciso clonar esse repositório localmente.
#### 8. Acessa no CLI (pela linha de comando) a pasta/diretório que vai querer criar o clone do repositório do GitHub.
#### 9. No site do GitHub acessa o repositório criado e em '<> Code', clica em 'Local' e depois em 'SSH', copia o link e volta no CLI.
#### 10. Agora com o link copiado e já tendo acessado o diretório, vai clonar a pasta, digita no CLI <git clone link_ssh> + enter
#### 11. Clone feito, pra confirmar só digita <ls> + enter, e verifica se o nome da pasta aparece.

Voltar para as [Instruções básicas](#instru).
