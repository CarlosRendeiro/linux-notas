# Tópicos — Linux Infra Notes

## Parte 1 - Terminal — Fundamentos
- [x] Abrir terminal, entender prompt (`Ctrl+Alt+T`)
- [x] Navegação: `pwd`, `ls`, `cd`, `cd ..`
- [x] Diferença entre usuário comum e `root`
- [x] `sudo` vs `su` / `su - usuario`
- [x] Sair de sessão root (`exit` / `Ctrl+D`)
- [x] Editor de texto no terminal (`nano`)
- [x] Permissões de arquivo (`ls -l`, `chmod`, `chown`)

## Parte 2 - Gerenciamento de pacotes
- [x] Rocky Linux: `dnf`
- [x] Ubuntu: `apt update` / `apt upgrade` / `apt install` / `apt remove`
- [ ] Gerenciamento de repositórios (PPA / repos dnf)
- [ ] `apt list --upgradable`

## Parte 3 - systemd / boot
- [x] `systemctl get-default`
- [x] Alternar entre `graphical.target` e `multi-user.target`
- [x] Boot direto em modo texto (VM Ubuntu configurada)
- [ ] Gerenciar serviços (`systemctl start/stop/enable/status`)
- [ ] Ver logs de serviço (`journalctl`)

## Parte 4 - PostgreSQL — Instalação e administração
- [x] Rocky Linux: PostgreSQL 17 + workaround porta 5433
- [x] Ubuntu: PostgreSQL 18.6 instalado e validado
- [x] Criar banco de dados (`createdb`)
- [x] Conectar ao banco (`psql -U ... -d ...`)
- [x] Simulação de recuperação: `DROP OWNED BY ... CASCADE` vs `REASSIGN OWNED BY`
- [ ] Gerenciar usuários/roles (`CREATE ROLE`, `GRANT`)
- [ ] Backup e restauração (`pg_dump`, `pg_restore`)
- [ ] Configuração de acesso remoto (`postgresql.conf`, `pg_hba.conf`)

## Parte 4 - PostGIS
- [x] Ativar extensão no banco (`CREATE EXTENSION postgis;`)
- [x] Verificar versão (`SELECT PostGIS_version();`)
- [ ] Carregar shapefile (`shp2pgsql` vs `ogr2ogr`/GDAL) — **em andamento**
- [ ] Consultas espaciais básicas (`ST_AsText`, `ST_MakePoint`, `ST_Distance`)
- [ ] Índices espaciais (`GIST`)
- [ ] Reprojeção de SRID (`ST_Transform`)

## Parte 5 - Ambientes de prática
- [x] Rocky Linux 9.8 / 10.2 (VirtualBox) — banco `geobd` original
- [x] Ubuntu 26.04 LTS (VirtualBox) — terminal puro + PostgreSQL/PostGIS do zero
