1. Por que o Linux recebeu esse nome?
    Porque o Linux é um free-software variante do Unix e foi criado por Linus Torvalds.
2. O que são daemons?
    São programas que executam instruções de modo a controlar(iniciar, reiniciar, parar, etc.) um serviço provido pelo SO.
3. O que é o shell?
    O shell do linux é a linha de comando (similar ao prompt de comando), que tem função de ser a ponte de comunicação do usuário e o kernel do SO e executar comandos escritos de modo a devolver resultados pelas saídas.
4. Por que é importante evitar executar o terminal como super-usuário?
    Porque logado como super usuário(root) se tem controle total sobre o sistema: ligar/desligar, adicionar/remover usuários, alterar senhas,instalar/remover aplicações,etc.
5. Qual botão do teclado completa o que o usuário escreve no terminal, de acordo com o contexto?
    O botão "tab". Além de completar, caso necessário ele mostra a lista de prováveis comandos a serem escritos.
6. Quais botões do teclado apresentam instruções escritas anteriormente?
    Os botões de setas para cima e para baixo.
7. Apresente os respectivos comandos no terminal para:
  (a) Obter mais informações sobre um comando.
     man + comando
  (b) Apresentar uma lista com os arquivos dentro de uma pasta.
    ls
  (c) Apresentar o caminho completo da pasta.
    pwd
  (d) Trocar de pasta.
    "cd + nome/caminho da pasta " para entrar na pasta e "cd .." para voltar para pasta anterior
  (e) Criar uma pasta.
    mkdir + nome da pasta
  (f) Apagar arquivos definitivamente.
    rm + nome do arquivo com formato
  (g) Apagar pastas definitivamente.
    rmdir + nome da pasta
  (h) Copiar arquivos.
    cp + arquivo origem com formato + arquivo destino com formato
  (i) Copiar pastas.
    cp -r + origem + destino
  (j) Mover arquivos.
    mv + arq origem + arq destino
  (k) Mover pastas.     
    mv + pasta origem + pasta destino
  (l) Renomear pastas.
    mv + pasta + novo nome da pasta
  (m) Apresentar o conteúdo de um arquivo.
    cat + arquivo com formato
  (n) Apresentar o tipo de um arquivo.
    file + arquivo
  (o) Limpar a tela do terminal.
    clear
  (p) Encontrar ocorrências de palavras-chave em um arquivo-texto.
    cat teste.txt | grep caio
  (q) Ordenar informações em um arquivo-texto.
    sort [opções] [arquivo]
  (r) Substituir ocorrências de palavras-chave em um arquivo-texto.
    sed -i 's/original/nova/g' arquivo
  (s) Conferir se dois arquivos são iguais.
    cmp [arquivo1] [arquivo2]
    diff [arquivo1] [arquivo2] (para arquivos de texto)
  (t) Escrever algo na tela.
    echo [escrita]
