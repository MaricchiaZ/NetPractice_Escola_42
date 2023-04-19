### Level 6
● Ajustar o ip da interface R1 para que combine com o ip fixado da interface A1.
● Ajustar o roteamento do cliente A para chegar à interface R1. (Mesmo ip).
● Router R destination para default.
● Destination da internet para o ip de A1.

### Level 7
● Mude todas as máscaras para final 252 ou /30
● O host de R11 é 1 e o de R12 é 254, coloque os outros de acordo e o host de R22 pode ser 193
e da C1 194.
● Todos os destinations são default. Coloque o next hop de acordo. Ex: de R1 para R21.

### Level 8
● O ip de R13 é o mesmo do next hop de R2.
● O ip de R21 é o mesmo de R2 -1 no host.
● R23 e R22 podem ser o mesmo ip de R21 apenas mudando o host para 1 e 17
respectivamente.
● Internet next hop é a interface R12.
● R1 destination é a mesma rede de R21, R22 e R23. Mude o host para 0 e tente uma máscara
de /27.

### Level 9
● Mude o início da R11 de 192 para 121. Para sair das redes reservadas e poder se comunicar
com a internet.
● Preencha a interface e cliente B e A de acordo.
● Mude os ips de C1 e R22 para 9 no início, para também não ser uma rede reservada. Use a
máscara /30 em ambos.
● R23 é o next hop do client D.
● R2 deve ter como next hop o ip de R13.
● Em R1 um destination deve ir para a rede de C1 e o outro para R23. Ambos next hop vão para
o ip de R21.
● Em internet um destination é o ip da R11 e o outro volta para a rede de C1. O último fica
como default mesmo.

### Level 10
● Ajustar o ip da interface H21 para se comunicar com o ip fixado de H11. E a máscara de ambos
é igual a da interface R11.
● Copiar o ip do client H4 para a interface R23 e mudar a máscara para a fixada em H41.
● O ip da R22 é o mesmo da R23 só mudando o host para 193. Depois ajuste a H31 para 194 e o
client H3 de acordo.
● Ajustar a máscara da R13 para final 252.
● A internet deve ter como destination o ip da R13, com 0 como host e /24.
● Em R1 coloca como destination a rede de R22 com o final 192 / 30.

### Ips reservados para Private Networks:
● 10.0.0.0 – 10.255.255.255
● 172.16.0.0 – 172.31.255.255
● 192.168.0.0 – 192.168.255.255
● 127.0.0.0 – 127.255.255.25
