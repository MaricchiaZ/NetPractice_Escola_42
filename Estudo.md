
Classes de ip
A   0     a   127 - 16.777.216 combinações
B   128   a   191 - 65.536 combinações
C   192   a   223 - 256 combinações
D   224   a   239 - (TESTES DE NOVAS TECNOLOGIAS)
E   240   a   255 - (MULTICASTS / UNICAST/ BROADCAST)

Redes 2 - IP, máscara de rede, gateway
(https://www.youtube.com/watch?v=yLgansF_h1w)

Um IP é composto por 32 bits 00000000.00000000.00000000.00000000 ou 4 octetos

Rede - envio de informações / envio de pacote de rede
    >Máscara da Rede (intervalo de IP que compõe uma rede)
Gateway - caminho que conecta uma rede em outra

Máscara da Rede (intervalo de IP que compõe uma rede)

### Entendendo a Rede

___________________________________ exemplo 1 __________________________________________________

Imagine uma rede  192.       168.         0.          1
                00000000.  00000000.   00000000.   00000000
Que usa essa máscara         redes               |  hosts (usuário final que recebe a rede)
Que usa essa máscara         redes (24 bits)     |  hosts (8 bits)

Nessa rede podemos ter HOSTS do IP    192.       168.         0.          0
ao (isso usa 8 bits que dá 256)       192.       168.         0.          255

De todos esses IPS do 192.168.0.0 ao 192.168.0.255 precisamos saber que o IP 192.168.0.0 não é atribuido a nenhum host ele é o IP DA REDE (ele que vai representar aquela rede), e o último ip, o 192.168.0.255 é chamado de IP BROADCAST, uma das máquinas da rede pode mandar info pra que as outras máquinas da mesma rede recebam; 
O QUE FAZ COM QUE TENHAMOS 254 HOSTS NESSA REDE


___________________________________ exemplo 2 __________________________________________________

Imagine uma rede  192.       168.         0.          1
                00000000.  00000000.   00000000.   00000000
Que usa essa máscara         redes                  |  hosts (usuário final que recebe a rede)
Que usa essa máscara         redes (25 bits)        |  hosts (7 bits)

Nessa rede podemos ter HOSTS do IP    192.       168.         0.          0
ao (isso usa 8 bits que dá 127)       192.       168.         0.          127

De todos esses IPS do 192.168.0.0 ao 192.168.0.127 precisamos saber que o IP 192.168.0.0 não é atribuido a nenhum host ele é o IP DA REDE (ele que vai representar aquela rede), e o último ip, o 192.168.0.127 é chamado de IP BROADCAST, uma das máquinas da rede pode mandar info pra que as outras máquinas da mesma rede recebam; 
O QUE FAZ COM QUE TENHAMOS 126 HOSTS NESSA REDE

Isso acaba criando uma sub_REDE de IPS do 192.168.0.128 ao 192.168.0.255 e que também tem 126 HOSTS NESSA REDE


___________________________________ exemplo 3 __________________________________________________

Imagine uma rede   10.        0.         0.          1 
E outra uma rede   10.        0.         2.          255 
                00000000.  00000000.   00000000.   00000000
Que usa essa máscara         redes            |  hosts (usuário final que recebe a rede)
Que usa essa máscara         redes (23 bits)  |  hosts (9 bits)

Nessa rede podemos ter HOSTS do IP    10.       0.         0.          0
ao (isso usa 9 bits que dá 512)       10.       0.         1.          255

De todos esses IPS do 10.0.0.0 ao 10.0.1.255 precisamos saber que o IP 192.168.0.0 não é atribuido a nenhum host ele é o IP DA REDE (ele que vai representar aquela rede), e o último ip, o 10.0.1.255 é chamado de IP BROADCAST, uma das máquinas da rede pode mandar info pra que as outras máquinas da mesma rede recebam; 
O QUE FAZ COM QUE TENHAMOS 512 HOSTS NESSA REDE

___________________________________ exemplo 4 __________________________________________________

A rede com a máscara de 22 bits pra REDE e 10 bits para os hosts de IPS do 10.0.0.0 ao 10.0.3.255 sendo que o IP 10.0.0.0 não é atribuido a nenhum host ele é o IP DA REDE (ele que vai representar aquela rede), e o último ip, o 10.0.3.255 é chamado de IP BROADCAST, FAZ COM QUE TENHAMOS 1022 HOSTS NESSA REDE (1024 tirando o nome da rede e o broadcast)

### Entendendo o Gateway

Duas máquinas 192.168.0.0 e 192.168.0.10, 
Imagine essa rede que usa essa máscara /24
Que usa essa máscara         redes (24 bits)     |  hosts (8 bits)

Logo essa rede vai do IP 192.168.0.0 ao 192.168.0.255, então essas máquinas podem se comunicar diretamente.

MAS

se uma dessas máquinas quer acessar um site na internet de IP 200.200.200.200 precisa passar pelo GATEWAY (que pode ser um modem, ou um roteador, ou mesmo um servidor de internet)

o GATEWAY conecta máquinas com redes FORA da rede delas.
O GATEWAY pode ser o primeiro IP válido de uma rede: 192.168.0.1
OU
o último IP válido 192.168.0.254

__________________________________________________________________________________________
O que é ser um host?
Host é todo e qualquer computador ou máquina ligada a uma rede por meio de um número de IP e domínio definido que tem como responsabilidade oferecer recursos, informações e serviços aos usuários. Também é conhecido como: hospedagem, hospedeiro ou anfitrião.

mascara - Determina quantos ips eu tenho na minha rede

gateway - Gateway pode ser classificado como “portal” ou “portão”. Ele é considerado uma passagem entre dois ambientes distintos. Ou ainda, em outras palavras, é um sistema ou equipamento encarregado de estabelecer a comunicação entre duas redes. Serve para fazer as comunicações entre as redes.

ip - endereço da rede.

Broadcast - é fazer uma transmissão de larga escala, comunicando com todos os dispositivos de uma mesma rede. “Broad” pode ser traduzido como amplo ou em larga escala; e “cast” pode ser traduzido como transmissão ou projeção

LoopBack - quando o computador se comunica com ele mesmo.

192.168... é uma rede privada para se comunicar com a internet precisa utilizar outros endereços de IP.
___________________________________________________________________________________________


LEVEL 1
{"routes":{},"ifs":{"A1":{"ip":"104.98.23.123"},"B1":{},"C1":{},"D1":{"ip":"211.191.227.70"}}}

LEVEL 2
{"routes":{},"ifs":{"A1":{"ip":"192.168.70.200"},"B1":{"mask":"/7"},"C1":{"ip":"10.0.0.1"},"D1":{"ip":"10.0.0.2"}}}

LEVEL 3
{"routes":{},"ifs":{"A1":{"mask":"255.255.255.0"},"B1":{"ip":"104.198.249.100","mask":"255.255.255.128"},"C1":{"ip":"104.198.249.110"},"S1":{}}}

LEVEL 4
{"routes":{},"ifs":{"A1":{"mask":"255.255.255.0"},"B1":{"ip":"109.38.113.130","mask":"255.255.255.0"},"R1":{"ip":"109.38.113.100","mask":"255.255.255.0"},"R2":{},"R3":{},"S1":{}}}

LEVEL 5
{"routes":{"Ar1":{"route":"default","gate":"32.230.246.126"},"Br1":{"gate":"143.233.247.254"}},"ifs":{"A1":{"ip":"32.230.246.124","mask":"255.255.255.0"},"B1":{"ip":"143.233.247.250","mask":"255.255.0.0"},"R1":{},"R2":{}}}

LEVEL 6
{"routes":{"Ar1":{"route":"default","gate":"107.253.35.226"},"Rr1":{"route":"default"},"Ir1":{"route":"107.253.35.254/25"}},"ifs":{"A1":{"mask":"255.255.255.128"},"R1":{"ip":"107.253.35.226"},"R2":{},"S1":{},"Somewhere on the Net":{},"I1":{}}}

LEVEL 7
{"routes":{"Ar1":{"route":"0.0.0.0/0","gate":"102.198.14.1"},"Cr1":{"route":"0.0.0.0/0","gate":"102.198.14.5"},"R1r1":{"route":"0.0.0.0/0","gate":"102.198.14.253"},"R2r1":{"route":"0.0.0.0/0","gate":"102.198.14.254"}},"ifs":{"A1":{"ip":"102.198.14.2","mask":"255.255.255.252"},"C1":{"ip":"102.198.14.6","mask":"255.255.255.252"},"R11":{"mask":"255.255.255.252"},"R12":{"mask":"255.255.255.252"},"R21":{"ip":"102.198.14.253","mask":"255.255.255.252"},"R22":{"ip":"102.198.14.5","mask":"255.255.255.252"}}}

LEVEL 8
{"routes":{"Cr1":{"route":"default","gate":"151.101.106.17"},"Dr1":{"route":"default","gate":"151.101.106.1"},"R1r2":{"route":"151.101.106.0/27","gate":"151.101.106.61"},"R1r3":{},"R2r1":{"route":"default"},"Ir1":{"gate":"163.131.250.12"}},"ifs":{"C1":{"ip":"151.101.106.18","mask":"255.255.255.252"},"D1":{"ip":"151.101.106.2"},"R12":{},"R13":{"ip":"151.101.106.62","mask":"255.255.255.252"},"R21":{"ip":"151.101.106.61","mask":"255.255.255.252"},"R22":{"ip":"151.101.106.17","mask":"255.255.255.252"},"R23":{"ip":"151.101.106.1","mask":"255.255.255.240"},"I1":{}}}

LEVEL 9
{"routes":{"Ar1":{"route":"default","gate":"121.168.22.1"},"Br1":{"route":"default","gate":"121.168.22.1"},"Cr1":{"gate":"9.0.0.2"},"Dr1":{"route":"default"},"R1r1":{"route":"","gate":""},"R1r2":{"route":"default","gate":"91.52.18.253"},"R1r3":{},"R2r1":{"gate":"91.52.18.254"},"Ir1":{"route":"9.0.0.0/28"},"Ir2":{"route":"121.168.22.0/25"},"Ir3":{"route":"default"}},"ifs":{"A1":{"ip":"121.168.22.2","mask":"255.255.255.128"},"B1":{"ip":"121.168.22.6","mask":"255.255.255.128"},"C1":{"ip":"9.0.0.1","mask":"255.255.255.252"},"D1":{"ip":"43.19.153.79","mask":"/18"},"R11":{"ip":"121.168.22.1"},"R12":{},"R13":{"ip":"91.52.18.254","mask":"255.255.255.0"},"R21":{"ip":"91.52.18.253"},"R22":{"ip":"9.0.0.2","mask":"255.255.255.252"},"R23":{"ip":"43.19.153.78"},"S1":{},"I1":{}}}

LEVEL 10
{"routes":{"H1r1":{},"H2r1":{},"H3r1":{"gate":"167.27.33.193"},"H4r1":{},"R1r1":{"route":"default"},"R1r2":{},"R1r3":{},"R2r1":{},"Ir1":{"route":"167.27.33.0/24"}},"ifs":{"H11":{"mask":"255.255.255.128"},"H21":{"ip":"167.27.33.3","mask":"255.255.255.128"},"H31":{"ip":"167.27.33.194","mask":"255.255.255.252"},"H41":{},"R11":{},"R12":{},"R13":{"mask":"255.255.255.252"},"R21":{},"R22":{"ip":"167.27.33.193","mask":"255.255.255.252"},"R23":{"ip":"167.27.33.129","mask":"255.255.255.192"},"S11":{},"I1":{}}}
