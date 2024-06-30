# Script Python para gerar o dataset simulado de estoque de produtos de tecnologia

import pandas as pd
import numpy as np
import random
from datetime import datetime, timedelta

# Definindo parâmetros
num_registros = 500  # número de registros no dataset
num_produtos = 50    # número de produtos diferentes
data_inicial = datetime(2023, 12, 31)  # data inicial
promo_probabilidade = 0.3  # probabilidade de promoção

# Lista de nomes de produtos de tecnologia
nomes_produtos = ['Smartphone', 'Tablet', 'Laptop', 'Desktop', 'Monitor', 'Impressora', 'Teclado', 'Mouse', 'Fone de Ouvido', 'Caixa de Som']

# Gerando dados
data = []
for _ in range(num_registros):
    for dia in range(365):
        data_evento = data_inicial + timedelta(days=dia)
        for produto_id in range(1, num_produtos + 1):
            nome_produto = random.choice(nomes_produtos)
            if random.random() < promo_probabilidade:
                flag_promocao = 1
            else:
                flag_promocao = 0
            quantidade_estoque = np.random.randint(20, 100)
            data.append([produto_id, nome_produto, data_evento.strftime('%Y-%m-%d'), flag_promocao, quantidade_estoque])

# Criando DataFrame
df = pd.DataFrame(data, columns=['ID_PRODUTO', 'NOME_PRODUTO', 'DATA_EVENTO', 'FLAG_PROMOCAO', 'QUANTIDADE_ESTOQUE'])

# Salvando como CSV
df.to_csv('historico_estoque_produtos.csv', index=False)
print("Dataset gerado e salvo com sucesso!")
