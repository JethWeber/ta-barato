# Tá Barato

**Tá Barato** é uma plataforma de e-commerce dinâmica e acessível, desenvolvida em **PHP** com banco de dados **SQLite**, perfeita para pequenos negócios ou projetos educacionais. Com uma interface moderna e responsiva, permite que visitantes explorem produtos, criem contas, façam login e realizem compras, enquanto administradores gerenciam produtos e usuários por meio de um painel intuitivo. Estilizado com **CSS** personalizado e projetado para ser leve, o Tá Barato é fácil de configurar e expandir, ideal para desenvolvedores que buscam uma solução prática de comércio eletrônico.

## 📋 Funcionalidades

- **Página Principal (`index.php`)**: Exibe uma lista de produtos com imagem, nome, categoria, preço e descrição, recuperados do banco de dados SQLite.
- **Autenticação**:
  - Login e registro de usuários (`login.php`, `crear_conta.php`).
  - Sessão de usuário com redirecionamento para o painel administrativo para o usuário `admin`.
  - Logout simples (`logout.php`).
- **Painel Administrativo (`admin/`)**:
  - Gerenciamento de produtos (`confg_prod.php`): CRUD (criar, ler, atualizar, deletar) de produtos.
  - Gerenciamento de usuários (`confg_user.php`): CRUD de usuários.
- **Banco de Dados SQLite**:
  - Tabela `produtos`: Armazena informações dos produtos (ID, imagem, nome, categoria, preço, descrição, data de cadastro).
  - Tabela `usuarios`: Armazena informações dos usuários (ID, imagem, nome, apelido, senha).

## 📂 Estrutura de Arquivos
site_loja/
├── admin/ <br>
│   ├── admin_panel.php       # Painel administrativo principal<br>
│   ├── confg_prod.php        # Gerenciamento de produtos (CRUD)<br>
│   └── confg_user.php        # Gerenciamento de usuários (CRUD)<br>
├── assets/<br>
│   ├── comprovativo/         # Diretório para comprovativos (se usado)<br>
│   ├── css/<br>
│   │   └── style.css         # Estilos principais do projeto<br>
│   ├── js/                   # Scripts JavaScript (se usados)<br>
│   └── uploads/              # Imagens de produtos e outros uploads<br>
├── clip.css                  # Estilos adicionais<br>
├── crear_conta.php           # Página de registro de usuários<br>
├── database12.sqbpro         # Arquivo de banco de dados (backup/teste)<br>
├── database.db               # Banco de dados SQLite principal<br>
├── database.sqbpro           # Arquivo de banco de dados (backup/teste)<br>
├── index.php                 # Página principal com lista de produtos<br>
├── loged.php                 # Página para usuários logados<br>
├── login.php                 # Página de login<br>
├── logout.php                # Script de logout<br>
├── process_login.php         # Processamento do login<br>
└── README.md                 # Documentação do projeto<br>



## 🛠️ Pré-requisitos

Para rodar o projeto localmente, você precisa de:

- **Servidor Web**: Apache2 (recomendado) ou Nginx.
- **PHP**: Versão 8.3 ou superior, com o módulo `sqlite3` habilitado.
- **SQLite**: Banco de dados leve, incluído no PHP.
- **Sistema Operacional**: Linux (ex.: Ubuntu, Linux Mint), Windows, ou macOS.

## ⚙️ Instalação e Configuração

Siga as instruções abaixo para configurar o projeto no seu sistema operacional.

### 🐧 Linux (Ubuntu, Linux Mint, etc.)

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/jethweber/ta-barato.git
   cd ta-barato
   sudo mv * /var/www/html/site_loja
   ```
   
2. **Instale dependências**:
    ```bash
    sudo apt update
    sudo apt install apache2 php libapache2-mod-php php-sqlite3
    ```
3. **Configure permissões**:
    ```bash
    sudo chown -R www-data:www-data /var/www/html/site_loja
    sudo chmod -R 755 /var/www/html/site_loja
    sudo chmod 664 /var/www/html/site_loja/database.db
    ```

4. **Configure o Apache2**:
     ```bash
    sudo chown -R www-data:www-data /var/www/html/site_loja
    sudo chmod -R 755 /var/www/html/site_loja
    sudo chmod 664 /var/www/html/site_loja/database.db
    ```
     - Edite ```/etc/apache2/sites-available/000-default.conf``` para permitir ```.htaccess```:
        ```apache
        <VirtualHost *:80>
          ServerAdmin webmaster@localhost
          DocumentRoot /var/www/html
          ErrorLog ${APACHE_LOG_DIR}/error.log
          CustomLog ${APACHE_LOG_DIR}/access.log combined
      
          <Directory /var/www/html>
              Options Indexes FollowSymLinks
              AllowOverride All
              Require all granted
          </Directory>
        </VirtualHost>
        ```  
      - Habilite o módulo ```rewrite```:
          ```bash
          sudo a2enmod rewrite
          sudo systemctl restart apache2
          ``` 
5. **Acesse o projeto**:

    - Abra o navegador e vá para http://localhost/site_loja.
    - Para o painel administrativo, faça login com:
        - Usuário: ```admin```
        - Senha: ```admin```


### 🪟 Windows

 1. **Instale um servidor web**:
    - Baixe e instale o XAMPP em ```https://www.apachefriends.org/```.
    - Inicie o Apache e o módulo PHP no painel de controle do XAMPP.

 2. **Clone o repositório**:
    - Use o Git Bash ou um cliente Git:
      ```bash
      git clone https://github.com/jethweber/ta-barato.git
      cd ta-barato
      ```
      
    - **Mova os arquivos para o diretório do XAMPP**:
      ```bash
      mv * C:\xampp\htdocs\site_loja
      ```
 3. **Configure permissões**:

    - No Windows, permissões são menos restritivas, mas certifique-se de que o diretório ```C:\xampp\htdocs\site_loja``` seja acessível pelo Apache.
   
 4. **Acesse o projeto**: 
    - Abra o navegador e vá para ```http://localhost/site_loja```.
    - Para o painel administrativo, use as credenciais ```admin/admin```.
   

### 🤝 Contribuindo

Contribuições são bem-vindas! Siga os passos abaixo:
1. **Faça um fork do repositório**.
2. **Crie uma branch para sua feature**:
       ```bash
       git checkout -b minha-feature
       ```
3. **Commit suas mudanças**:
    ```bash
    git commit -m "Adiciona minha feature"
    ```
4. **Envie para o repositório**:
    ```bash
    git push origin minha-feature
    ```

### 📬 Contato

Para dúvidas, sugestões ou suporte, entre em contato com o criador:
  - Nome: Jeth Weber
  - E-mail: jethweber@gmail.com
  - WhatsApp: +244 954629524
