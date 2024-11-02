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