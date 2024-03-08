**OBS**: Essa documentação e para fins didáticos

O que é Google dorking?

É uma técnica hacker que usa o Buscador do Google para encontrar brechas de segurança na configuração ou nos códigos utilizados pelos sítios web.

## Folha de dica

---------------------------------------------------------------------------

Faz pesquisa de arquivo especifico e conteúdo

* **Filetype:** tipo do arquivo "O que vc quer que tenha nele"

    - **Ex:** filetype: pdf "piscina"

---------------------------------------------------------------------------

Pesquisa uma URL que corresponda a(as) palavras-chave.

* **inurl:** "Palavra-chave"

    -   **EX:** inurl: "piscina"

Procura um URL que contenha todas as palavras-chave na consulta

* **allinurl:** "Palavras-chaves"

     -   **EX:** allinurl: "piscina,praia,céu"

---------------------------------------------------------------------------

Pesquisa ocorrências de palavras-chave que corresponda ao título

* **intitle:** "Titulo"

    -   **EX:** intitle: "piscina"

Pesquisa ocorrências de grupo de palavras-chave que corresponda ao título

* **allintitle** "Titulos"

    - **EX:**  allintitle: "piscina,praia,céu"

---------------------------------------------------------------------------

Pesquisa sobre o site e tudo disponível sobre ele

* **site:** domínio do site

    - **EX:** site: "www.exemplo.com"

---------------------------------------------------------------------------

Pesquisa links externos da página

* **links** "palavras-chaves"

    - **EX:**  link:"Piscina"

---------------------------------------------------------------------------

Pesquisa por palavras-chaves 

* **intext** "palavras-chaves"

    - **EX:**  intext "piscina"

---------------------------------------------------------------------------

Localiza números específicos

* **numrange:** "Números"

    - **EX:** numrange: "1-10" (Pesquisa de 1 a 10)

    - **EX:** numrange: "30"

---------------------------------------------------------------------------

Pesquisar dentro de um intervalo de datas específico. (Usando _filetype_)

* **before/after**

    - **EX:** filetype:pdf & (before:1899-02-01 after:1899-04-01)

---------------------------------------------------------------------------

Pesquisa palavra-chave que estão escritas na url (Nesse não há (" "))

* **inanchor:** palavra-chave  

    - **EX:** inanchor: praia

Pesquisa um grupo de palavras-chave que estão escritas na url (Nesse não há (" "))

* **allinanchor:** palavras-chaves

    - **EX:** allinanchor: praia,céu,mar 

---------------------------------------------------------------------------

Especifico para blogs pesquisa postes com o nome do autor

* **allinpostauthor:** "Palavra-chave"

    - **EX:** allinpostauthor:"praia,céu,mar"

---------------------------------------------------------------------------

Pesquisa sobre páginas relacionas 

* **ralated:** domínio

    - **EX:** related: www.exemplo.com

---------------------------------------------------------------------------

Mostra a versão da página da web que o Google possui em cache.

* **cache:** url

    - **EX:** cache: www.google.com

Colocar um (~) antes de uma palavra informa ao motor de busca que você sinômimos daquela palavra


## Operadores 


* **AND(&)** (Proucura algo relacionado ao site)

    - site:www.clickjogos.com  &  "news"

* **OR(|)** (Pesquisa o termo ou algo equivalente)

    - site: facebook.com & jogos | players

* **NOT(!)** Exclui esse resultado da busca

    - site: facebook.com & jogos ! players