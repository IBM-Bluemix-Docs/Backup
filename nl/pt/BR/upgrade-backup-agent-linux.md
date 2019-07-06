---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, upgrade agent, Linux

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Fazendo upgrade do agente de software de backup para Linux
{: #UpgradeinLinux}

É possível fazer download do agente de backup mais recente da seção de links rápidos do Painel do portal do {{site.data.keyword.backup_notm}}.
{:tip}

Seguir o processo de upgrade assegura que é possível fazer upgrade do agente do {{site.data.keyword.backup_notm}} sem perder o registro

1. Efetue login em seu host no nível raiz.
2. Faça download da versão mais recente do agente.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. Extraia o conteúdo do arquivo transferido por download.

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. Acesse o diretório de instalação recente.
   ```
   cd Agent-Linux-x64-8.11.5251/4
   ```

5. Execute o script de instalação.
   ```
   ./install.sh
   ```
   {:pre}

6. Responda aos prompts selecionando seu idioma, selecionando `N` para não registrar o computador como um novo host e `A` para criptografar dados usando o método de criptografia integrado.

7. Se a instalação for bem-sucedida, ela será registrada em `/opt/BUAgent/Install.log`.
