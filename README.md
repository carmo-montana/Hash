# O que é um Hash?
- Um hash é uma função matemática que transforma um conjunto de dados (como um arquivo ou uma string) em uma sequência de caracteres de tamanho fixo. Esses hashes são únicos para cada conjunto de dados, ou seja, se você alterar um único bit no arquivo ou na string, o hash resultante será completamente diferente. Hashes são amplamente utilizados para verificar a integridade de arquivos, armazenar senhas de forma segura, entre outras aplicações.

## Calculando Hashes usando Comandos do Linux
1. No Linux, existem comandos específicos para calcular hashes de arquivos ou strings. Vamos ver alguns dos mais comuns:

`md5sum`
- O MD5 é um algoritmo de hash que gera um valor de 128 bits (32 caracteres hexadecimais). Embora não seja mais considerado seguro para criptografia, ainda é útil para verificar a integridade de arquivos.

## Exemplo:

bash
`md5sum /etc/passwd`

Saída:
`a6f07227b6ab47f6486aa3b8ec5a41de  /etc/passwd`

`a6f07227b6ab47f6486aa3b8ec5a41de`: Este é o hash MD5 do arquivo /etc/passwd.
/etc/passwd: Este é o arquivo que foi processado.

#

`sha1sum`
- O SHA-1 é um algoritmo de hash que gera um valor de 160 bits (40 caracteres hexadecimais). Assim como o MD5, o SHA-1 também não é mais considerado seguro para criptografia, mas ainda é usado para verificar a integridade de arquivos.

## Exemplo:

bash
`sha1sum /etc/passwd`

Saída:
`d928c9de9f3de0b8ab71eb453093e400bee99b6c  /etc/passwd`

`d928c9de9f3de0b8ab71eb453093e400bee99b6c`: Este é o hash SHA-1 do arquivo /etc/passwd.

#

`sha256sum`
- O SHA-256 é um algoritmo de hash que gera um valor de 256 bits (64 caracteres hexadecimais). É mais seguro que o MD5 e o SHA-1, e é amplamente utilizado em aplicações de segurança.

## Exemplo:

bash
`sha256sum /etc/passwd`

Saída:
`e277ddd66709224518de393047a63f048b74dd9b73b1de49a24f5362d41427dd  /etc/passwd`

`e277ddd66709224518de393047a63f048b74dd9b73b1de49a24f5362d41427dd`: Este é o hash SHA-256 do arquivo /etc/passwd.

#

`sha512sum`
- O SHA-512 é um algoritmo de hash que gera um valor de 512 bits (128 caracteres hexadecimais). É ainda mais seguro que o SHA-256 e é usado em aplicações que exigem um alto nível de segurança.

## Exemplo:

bash
`sha512sum /etc/passwd`

Saída:
`273a39c960f815dbba1f1a4ca198720780ee192fc2dbcd5e6e6ed54122c564879b99ccb73daa62c6c7b49dbb3c97bb8ec1eebf211f668c49f2bbe037b8738eb5 /etc/passwd`

`273a39c960f815dbba1f1a4ca198720780ee192fc2dbcd5e6e6ed54122c564879b99ccb73daa62c6c7b49dbb3c97bb8ec1eebf211f668c49f2bbe037b8738eb5`: Este é o hash SHA-512 do arquivo /etc/passwd.

#

# Calculando Hash de uma String
- Você também pode calcular o hash de uma string diretamente usando o comando echo com a opção -n (que evita a adição de uma nova linha no final da string).

## Exemplo:

bash
`echo -n "hacking ético" | sha256sum`

Saída:
`285f81a21734ec2f9f667dee22490ec6053e414f9f35efb2170f1b966279916c  -
285f81a21734ec2f9f667dee22490ec6053e414f9f35efb2170f1b966279916c`: Este é o hash SHA-256 da string "hacking ético".

### Indica que a entrada foi recebida via pipe (não foi um arquivo).

#

# Calculando Hashes usando OpenSSL
- O OpenSSL é uma ferramenta poderosa que suporta uma variedade de algoritmos de criptografia, incluindo hashes. Vamos ver como usá-lo para calcular hashes.

## Listando Algoritmos Suportados
- Para ver todos os algoritmos de hash suportados pelo OpenSSL, você pode usar o comando:

bash
`openssl list -digest-algorithms`

Isso listará todos os algoritmos de hash disponíveis, como MD5, SHA-1, SHA-256, SHA-512, etc.

#

## Calculando Hash de um Arquivo
- Você pode usar o comando openssl dgst para calcular o hash de um arquivo.

## Exemplo:

bash
`openssl dgst -sha3-256 /etc/passwd`

Saída:
`SHA3-256(/etc/passwd)=
6b86b273ff34fce19d6b804eff5a3f5747ada4eaa22f1d49c01e52ddb7875b4b
6b86b273ff34fce19d6b804eff5a3f5747ada4eaa22f1d49c01e52ddb7875b4b`: Este é o hash SHA3-256 do arquivo /etc/passwd.

#

## Calculando Hash de uma String
- Você também pode calcular o hash de uma string usando o OpenSSL.

## Exemplo:

bash
`echo -n "linux" | openssl dgst -rmd160`

Saída:
`(stdin)= 89939edf840d6edd260dcf326eb71beed79f776d
89939edf840d6edd260dcf326eb71beed79f776d`: Este é o hash RIPEMD-160 da string "linux".

#

## Ferramentas Online para Calcular Hashes
- Se você preferir uma interface gráfica ou não tiver acesso a um terminal Linux, pode usar ferramentas online para calcular hashes. Um exemplo é o site:

https://emn178.github.io/online-tools/sha512.html

### Neste site, você pode inserir uma string ou fazer upload de um arquivo, e ele calculará o hash usando vários algoritmos, como SHA-512, SHA-256, MD5, etc.

# Resumo
- Hashes são usados para verificar a integridade de arquivos e strings.

- No Linux, você pode usar comandos como md5sum, sha1sum, sha256sum, e sha512sum para calcular hashes de arquivos.

- O OpenSSL é uma ferramenta poderosa que suporta uma variedade de algoritmos de hash.

- Ferramentas online também estão disponíveis para calcular hashes de forma rápida e fácil.

# Prática
- Agora que você entende os conceitos básicos, experimente calcular hashes de diferentes arquivos e strings no seu terminal Linux. Use os comandos que aprendemos e explore as opções disponíveis no OpenSSL. Quanto mais você praticar, mais confortável ficará com esses conceitos.
