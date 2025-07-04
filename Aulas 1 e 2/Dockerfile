FROM python:3.13.5-alpine3.22

# Define o diretório de trabalho dentro do contêiner
WORKDIR /app

# Copia o arquivo requirements.txt para dentro do contêiner e instala as dependências
COPY requirements.txt .

# Install Rust
RUN apk add --no-cache rust cargo

# Usamos --no-cache-dir para evitar o uso de cache de pacotes, reduzindo o tamanho da imagem Python
RUN pip install --no-cache-dir -r requirements.txt

# Copia o restante da aplicação para o diretório de trabalho
COPY . .

# Comando para rodar a aplicação usando uvicorn
EXPOSE 8000

# o host 0.0.0.0 permite que a aplicação seja acessada externamente ao container
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]

# MARVEL
# ELLIS
# 