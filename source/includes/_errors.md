# Erros

O projeto Midas usa os seguintes códigos de erros:

Código | Significado
---------- | -------
400 | Bad Request -- Sua solicitação é inválida.
401 | Unauthorized -- A solicitação não foi concluída porque a autenticação falhou ou a chave de API fornecida é inválida.
403 | Forbidden -- O acesso está proibido para usuários não autorizados.
404 | Not Found -- O item especificado não pode ser encontrado.
405 | Method Not Allowed -- Você tentou acessar o item com um método inválido.
406 | Not Acceptable -- Você solicitou um formato que não é JSON.
410 | Gone -- O item solicitado foi removido de nossos servidores.
429 | Too Many Requests -- Você está solicitando itens demais! Diminua a velocidade!
500 | Internal Server Error -- Tivemos um problema com nosso servidor. Tente novamente mais tarde.
503 | Service Unavailable -- Estamos temporariamente fora do ar para manutenção. Por favor, tente novamente mais tarde.
