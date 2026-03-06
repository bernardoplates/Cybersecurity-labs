Nesta aula eu tinha a misão de investigar um e-mail suspeito.

A atividade solicitava informações básicas, intermediárias e avançadas sobre o e-mail. Desde N° de protocolo, e endereços até registro SPF, DMARC e Hash SHA256.

Utilizei algumas ferramentas para conseguir atingir os resultados necessários. Este foi meu passo a passo:

1. Descobrir: Qual N° de ref., e-mail source, e-mail destination.
Apenas li e interpretei o e-mail para pegar estas informações.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fffae6f1-02bd-4211-8372-4cc0912b9e09" />


3. Qual o IP de origem.
Inspecionando o e-mail no seu código fonte pelo Thunderbird, consegui achar o valor de IP originário do e-mail. Um pouco mais complexo, mas nada impossível.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/81a07c83-bd8e-479f-bbfc-08ebca96b436" />


4. De quem é este IP (Qual domínio/DNS).
Usei uma ferramenta online "IP WHOIS" (https://www.whatismyip.com/ip-whois-lookup/) para descobrir o nome da organização.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/39e81c15-ee67-4080-b936-06c0d878ae23" />

5. Qual é o registro SPF e DMARC para o domínio do recebidor.
Utilizei um site chamado DMARCian (https://dmarcian.com/domain-checker/) para checkar estes valores.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9f7bb729-342b-47d7-a44d-31001988f8c5" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dddb5279-1916-419e-b6d6-7cf0cb96c794" />

6. Qual o nome do anexo.
No e-mail havia um anexo e eu precisava descobrir o nome dele, foi algo simples igual a tarefa N° 1.

7. Qual o hash SHA256 do anexo do arquivo.
Pelo e-mail thunderbird eu baixei o anexo na máquina virtual, e então pelo terminal eu usei os seguintes comandos:

"pwd"
"ls"
"sha256sum *nomedoarquivo*"

<img width="971" height="953" alt="image" src="https://github.com/user-attachments/assets/c75cdbf4-e69a-4430-9a15-170c71a8f161" />


então consegui o cósigo hash do anexo.

8. Qual tamanho em KB do anexo.
Entrei nas propriedades do anexo e o descobri.

9. Qual a extensão real do anexo.
Usei o site "VirusTotal" e coloquei o SHA256 do anexo, então lá consegui a real extensão dele. (.rar)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/37c88af3-49be-4ec0-85ab-c2487192cb97" />
