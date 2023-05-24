# subspace не актуально

0. Подготовка

В кавычках указываем свой адрес и произвольное имя ноды

<code>SUBSPACE_WALLET_ADDRESS="адрес для получения вознаграждения"</code>

<code>SUBSPACE_NODE_NAME="имя вашей ноды"</code>

В данной фазе максимальный размер плота 100 гигабайт

Можно указать меньше

<code>SUBSPACE_PLOT_SIZE="100G"</code>

записываем переменные

<code>echo 'export SUBSPACE_WALLET_ADDRESS='$SUBSPACE_WALLET_ADDRESS >> $HOME/.bash_profile</code>

<code>echo 'export SUBSPACE_NODE_NAME="'${SUBSPACE_NODE_NAME}'"' >> $HOME/.bash_profile</code>

<code>echo 'export SUBSPACE_PLOT_SIZE='$SUBSPACE_PLOT_SIZE >> $HOME/.bash_profile</code>


1. Установка DOCKER (Опиционально)

<code>sudo -i</code>

<code>cd $HOME</code>

<code>apt -qq update && apt -qq install curl wget -y && apt -qq purge docker docker-engine docker.io containerd docker-compose -y </code>

<code>rm /usr/bin/docker-compose /usr/local/bin/docker-compose</code>

<code>curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh && systemctl restart docker</code>

<code>curl -SL https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose</code>

<code>chmod +x /usr/local/bin/docker-compose && ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose</code>


2. Установка SUBSPACE

<code>mkdir subspace && cd subspace</code>

<code>wget -qO - https://raw.githubusercontent.com/mrraange/subspace/main/docker-compose.yml | envsubst > docker-compose.yml</code>

3. Запуск

<code>docker-compose up -d</code>


просмотр логов

<code>docker-compose logs --tail=1000 -f</code>

Удаление 

<code>cd $HOME/subspace</code>

<code>docker-compose down -v</code>

<code>cd $HOME && rm -rf $HOME/subspace/</code>

