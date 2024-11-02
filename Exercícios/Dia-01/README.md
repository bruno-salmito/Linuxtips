## Desafio do primeiro dia
Sem nenhum segredo, apenas coloque o Nginx para rodar! Lembre-se, ele deve rodar na porta 80 do container e do Servidor da LINUXtips.
Você tem duas abas, uma do Terminal Linux e outra com o Navegador!

## Resolução 
````
docker container run -d -p 80:80 nginx
````

## Dockerfile
````
# Usa a imagem oficial do Nginx como base
FROM nginx:latest

# Copia o arquivo de configuração do Nginx para o container (opcional)
# COPY nginx.conf /etc/nginx/nginx.conf

# Copia o arquivo index.html
COPY site/index.html /usr/share/nginx/html

# Exponha a porta 80 para permitir o tráfego HTTP
EXPOSE 80

# Iniciar o Nginx no container
CMD ["nginx", "-g","daemon off;"]
````
