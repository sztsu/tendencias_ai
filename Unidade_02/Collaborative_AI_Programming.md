# Programação Assistida e Automação com IA

## Identificação
- Nome: Gustavo Negreiros Pereira
- Turma: Tendências em Ciência da Computação
- Data: 10/09/2026
- Ferramenta de IA utilizada: Gemini

## 1. Problema
Automatizar a consulta de informações de endereço a partir de um CEP fornecido pelo usuário, consumindo uma API REST pública (ViaCEP). Essa automação é útil para agilizar o preenchimento de formulários ou validar dados espaciais sem intervenção manual prolongada.

## 2. Entrada
Uma string contendo o CEP desejado fornecida via terminal (o programa deve aceitar CEPs com 8 dígitos numéricos, com ou sem o traço).

## 3. Processamento
O script recebe o dado, realiza uma limpeza do traço (se houver), valida se possui exatamente 8 dígitos e faz uma requisição HTTP `GET` para o endpoint da API. Em seguida, converte o payload de resposta (JSON) para um dicionário Python e trata possíveis erros (como falta de conexão ou CEP inexistente).

## 4. Saída esperada
O programa deve exibir no terminal as informações extraídas formatadas (CEP, Logradouro, Bairro, Cidade e UF) ou uma mensagem de erro clara caso o CEP seja inválido ou não exista.

## 5. Prompt utilizado
"olá, vamos fazer uma ativiade para a faculdade relacionada a progamaçao, irá ser postado no GITHUB e se trata de 'API de consulta de CEP, realize requisições HTTP e manipue payloads JSON.'"

## 6. Código inicial
```python
import requests

def consultar_cep(cep):
    cep = cep.replace("-", "").strip()
    
    if len(cep) != 8:
        print("Erro: O CEP deve conter 8 dígitos.")
        return

    url = f"[https://viacep.com.br/ws/](https://viacep.com.br/ws/){cep}/json/"
    
    try:
        response = requests.get(url)
        if response.status_code == 200:
            dados_cep = response.json()
            if "erro" in dados_cep:
                print("Erro: CEP não encontrado na base de dados.")
            else:
                print(f"CEP: {dados_cep.get('cep')}")
                print(f"Logradouro: {dados_cep.get('logradouro')}")
                print(f"Bairro: {dados_cep.get('bairro')}")
                print(f"Cidade/UF: {dados_cep.get('localidade')}/{dados_cep.get('uf')}")
        else:
            print(f"Erro na requisição: Status {response.status_code}")
    except requests.exceptions.RequestException as e:
        print(f"Erro de conexão: {e}")

if __name__ == "__main__":
    cep_input = input("Digite o CEP que deseja consultar: ")
    consultar_cep(cep_input)