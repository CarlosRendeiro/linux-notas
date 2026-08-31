🐧 Linux (Rocky Linux / Ubuntu)

Anotações práticas e scripts desenvolvidos nos blocos de estudo, focados em administração de sistemas Linux voltados a infraestrutura e ambientes geoespaciais (PostgreSQL/PostGIS).

Mostrar Imagem Mostrar Imagem Mostrar Imagem Mostrar Imagem

📑 Índice
Conteúdo
Ambientes praticados
Rocky Linux
Ubuntu — Terminal e PostGIS
Próximos passos
📋 Conteúdo
Gestão de permissões e utilizadores
Comandos essenciais de terminal (RHEL family e Debian/Ubuntu family)
Configuração de banco de dados geoespacial (PostgreSQL/PostGIS)
Scripts de automação de tarefas repetitivas
🖥️ Ambientes praticados
Sistema	Uso principal
Rocky Linux 9.8 / 10.2 (VirtualBox)	Ambiente original PostgreSQL/PostGIS (banco geobd, workaround porta 5433)
Ubuntu 26.04 LTS (VirtualBox)	Prática de terminal puro (boot em modo texto) + PostgreSQL/PostGIS do zero
🔴 Rocky Linux
Comandos essenciais de terminal (Rocky Linux / RHEL family)
Configuração de PostgreSQL 17 + PostGIS em Rocky Linux 9.8 e 10.2
Workaround de porta (5433) para acesso ao PostgreSQL no servidor Linux
Simulação prática de recuperação de banco: DROP OWNED BY ... CASCADE (destrutivo) vs REASSIGN OWNED BY (correto), num cenário de consultoria DBA geoespacial (PostgreSQL/PostGIS + ArcGIS SDE)
🟠 Ubuntu — Terminal e PostGIS
Fundamentos de terminal
Navegação básica: pwd, ls, cd
Diferença entre usuário comum e root; sudo vs su
Edição de arquivos com nano
Permissões de arquivo (ls -l, chmod, chown)
Atualização do sistema
bash
sudo apt update
sudo apt upgrade
Boot direto em modo texto (sem interface gráfica)
bash
systemctl get-default
sudo systemctl set-default multi-user.target
sudo reboot

Para reverter à interface gráfica:

bash
sudo systemctl set-default graphical.target
PostgreSQL + PostGIS do zero
bash
psql --version
# psql (PostgreSQL) 18.6 (Ubuntu 18.6-0ubuntu0.26.04.1)

sudo -u postgres createdb geobd
sudo -u postgres psql geobd

Dentro do psql:

sql
CREATE EXTENSION postgis;
SELECT PostGIS_version();
-- 3.6 USE_GEOS=1 USE_PROJ=1 USE_STATS=1
🔜 Próximos passos
Carregar shapefile no banco geobd (comparar shp2pgsql vs ogr2ogr/GDAL)
Consultas espaciais básicas (ST_AsText, ST_MakePoint, ST_Distance)
Índices espaciais (GIST) e reprojeção de SRID (ST_Transform)
Gerenciamento de serviços via systemctl e leitura de logs (journalctl)

📍 Parte da minha trilha de especialização geoespacial full-stack (PostGIS → GeoPandas/FastAPI → React/OpenLayers).
