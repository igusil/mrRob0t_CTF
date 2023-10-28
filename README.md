# mrRob0t_CTF
**********************************************************************************************************************************
Fiz o acesso a pagina com o ip disponibilizado, e realizei o scan de diretorios com dirb, o mesmo poderia ter sido realizado manualmente.

![Screenshot from 2023-10-26 23-37-33](https://github.com/igusil/mrRob0t_CTF/assets/89313216/fc568261-9780-4e23-81ee-f99a058f4300)


verifiquei robots, onde encontrei a first flag txt e um arquivo dic
![Screenshot from 2023-10-26 23-39-12](https://github.com/igusil/mrRob0t_CTF/assets/89313216/4602348d-db99-4d8b-9036-054a3c99505f)

o passo seguinte foi verificar o arquivo dic, onde pude ver que tinha varias palavras repetidas.
usei o sort para deixar em ordem alfabetica e o parametro uniq, onde salvei em um arquivo txt, provavelmente usaria esse arquivo em brute force.

![Screenshot from 2023-10-26 23-57-58](https://github.com/igusil/mrRob0t_CTF/assets/89313216/b3a5056e-1e3a-46c6-9036-3da12490f9fb)

então fui até wp-login, pode identificar no scan realizado no inicio, e na wordlist pude localizar nomes relacionados ao CTF.
foi onde identifiquei um usuário pelo erro apresentado na tela ao errar o password, faltava no momento apenas a senha. 
\n
ERROR: The password you entered for the username elliot is incorrect.
![Screenshot from 2023-10-27 00-18-33](https://github.com/igusil/mrRob0t_CTF/assets/89313216/f7d92c4c-94e7-4daa-89b8-c1d6b41961ff)

Decidi interceptar a conexão com burp e realizar o brute force com os parametros.
![Screenshot from 2023-10-27 00-29-40](https://github.com/igusil/mrRob0t_CTF/assets/89313216/3880017a-e207-40ea-8ead-b3ce273e0952)

usei o hydra para realizar o brute force 
ao passar o parametro, adcione "/wp-login.php:" e altere o user e password para ^USER^ ^PASS^

![Screenshot from 2023-10-27 00-37-14](https://github.com/igusil/mrRob0t_CTF/assets/89313216/32702764-8b81-4741-a87f-ed7315a5245e)

Ao finalizar realizamos o login e teremos a seguinte tela.
![Screenshot from 2023-10-27 23-35-58](https://github.com/igusil/mrRob0t_CTF/assets/89313216/507b7186-306a-4269-b7fd-e13aede2fba2)

iremos buscar campos de upload para tentar um shell reverso.

![Screenshot from 2023-10-27 23-55-52](https://github.com/igusil/mrRob0t_CTF/assets/89313216/37c9ffd9-ecf8-48d0-8b49-4a415b6e5a97)

altere o shell de acordo com seu ip e porta que deseja usar

**********************************************************************************************************************************
