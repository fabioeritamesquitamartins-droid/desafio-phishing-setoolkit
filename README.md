# Desafio de Cybersecurity: Phishing para Captura de Credenciais com SEToolkit

## 📝 Descrição do Projeto
Este projeto foi desenvolvido como parte de um desafio prático pela plataforma **DIO (Digital Innovation One)**. O objetivo principal foi compreender os mecanismos de ataques de engenharia social na prática, utilizando a ferramenta **Social-Engineer Toolkit (SEToolkit)** integrada ao ecossistema do **Kali Linux** para simular uma página de login falsa (*Credential Harvester*).

> **Nota de Contexto Técnico:** Durante a execução do laboratório em ambiente controlado, optou-se pela utilização dos modelos pré-configurados locais da ferramenta (*Web Templates* voltados ao Google) para contornar as restrições rígidas de segurança de scripts externos e cabeçalhos de proteção (como HSTS e X-Frame-Options) do domínio original proposto. O fluxo de captura funcionou de forma idêntica e perfeitamente bem-sucedida.

---

## 🛠️ Ferramentas Utilizadas
*   **Sistema Operacional:** Kali Linux (executado em Máquina Virtual via Oracle VM VirtualBox)
*   **Ferramenta do Ataque:** Social-Engineer Toolkit (SEToolkit)
*   **Navegador de Testes:** Mozilla Firefox (interno à VM)

---

## 🚀 Passo a Passo da Execução

1.  **Abertura da Ferramenta:** O terminal do Kali Linux foi iniciado e o comando `sudo setoolkit` foi executado para obter privilégios de administrador.
2.  **Seleção do Vetor:** No menu principal, foi selecionada a opção `2) Website Attack Vectors`.
3.  **Definição do Método:** A escolha seguiu para a opção `3) Credential Harvester Attack Method` para preparar o servidor focado em capturar formulários de texto.
4.  **Configuração de Origem:** Selecionou-se a opção `1) Web Templates` para carregar páginas clonadas que funcionam localmente.
5.  **Configuração de Rede:** O endereço IP local da máquina virtual (`192.168.-.-`) foi confirmado como o servidor de escuta (POST back).
6.  **Ativação do Template:** Foi escolhido o template numérico correspondente ao **Google** (Opção 2), iniciando o servidor web na porta padrão `80`.

---

## 📊 Resultados Obtidos

Após o servidor ficar ativo, o navegador Firefox interno do Kali Linux foi utilizado para acessar o endereço IP local. Uma réplica exata da interface de autenticação do Google foi exibida.

Ao inserir credenciais fictícias de teste (`Email=teste@gmail.com` e `Password=teste123`), o formulário realizou o envio dos dados. O terminal do SEToolkit interceptou a requisição e expôs os dados transmitidos em texto claro no painel, conforme registrado na evidência do projeto.

Os parâmetros críticos capturados foram:
*   `POSSIBLE USERNAME FIELD FOUND: Email=teste@gmail.com`
*   `POSSIBLE PASSWORD FIELD FOUND: Password=teste123`

O arquivo de evidência visual foi devidamente salvo no repositório com o nome **`desafio-phishing-setoolkit.png`**.

---

## 🛡️ Conclusão e Aprendizado
A atividade permitiu visualizar como páginas de autenticação podem ser facilmente replicadas de forma local e quão suscetíveis usuários podem ser a ataques de engenharia social se não avaliarem criticamente a barra de endereços (URL/IP) do navegador. 

**Aviso Legal:** Este laboratório foi realizado estritamente para fins educacionais e de conscientização em segurança cibernética, simulando técnicas de defesa e análise de vulnerabilidades em um ambiente isolado.

