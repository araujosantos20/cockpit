# Cockpit

![Logo do Cockpit](cockpit.png)

## O que é?

Cockpit é um software de gerenciamento do seu sistema ou servidor, onde você utiliza ele no seu navegador web. Lá você tem diversas informações de contas que tem, memória, arquivos, últimas atualizações feitas no seu Linux, entre outras coisas.<br>

Uma coisa interessante é que com o Cockpit, é possível acessar diversos servidores que estejam na mesma rede que você apenas colocando o IP da máquina que esteja rodando o serviço. E assim poder gerenciar o serviço e visualizar de uma forma melhor o que está acontecendo.<br>

Agora eu quero lhe mostrar como instalar o Cockpit na sua máquina.

## Como instalar o Cockpit

Para sistemas operacionais como Fedora ou Ubuntu é bem simples:

Para Ubuntu é só digitar:

```
sudo apt-get install cockpit
```

E então dizer para o que o Ubuntu perguntar

---

Para o fedora é bem parecido só vai mudar uma única coisa

```
sudo dnf install cockpit
```

Desta forma é só ir em seu navegador web e digitar 'https://localhost:9090' e assim será aberto o seu Cockpit com o seu sistema operacional pedindo seu usuário e senha. Caso você esteja acessando o servidor de outra máquina, troque o `localhost` pelo IP da máquina que está rodando o serviço. O `9090` é a porta de comunicação, certifique-se qual sua porta de comunicação, a porta padrão do Cockpit é `9090`.

Eu utilizei a máquina virtual para fazer o Cockpit e então defini o número da minha porta de comunicação, veja abaixo:

![Porta de comunicação](comunicacao.png)

---

Não é dificil, mas em alguns sistemas é diferente e aqui irei te ensinar como fazer a instalação no OpenSUSE.

Primeiro é necessário adicionar o link para ele encontre o local para fazer o download

```
zypper addrepo https://download.opensuse.org/repositories/home:Ximi1970:Cockpit/15.5/home:Ximi1970:Cockpit.repo
```

Após isso, utilize este comando

```
zypper refresh
```

E então finalmente faremos o download

```
zypper install cockpit
```

---

Agora Iremos ativá-lo

Use

```
zypper in cockpit
```

Após isso, escreva estes 3 comandos

```
systemctl enable --now cockpit.socket
```

```
firewall-cmd --permanent --zone=public --add-service=cockpit
```

```
firewall-cmd --reload
```

Após isso, é só entrar pelo navegador e usar as dicas que falei inicialmente e finalmente você irá conseguir utilizar o seu cockpit. Espero que tenha gostado da dica e até a próxima.
