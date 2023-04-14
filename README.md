# TestEst-gioJob-Rotation
Resultados do Teste para Estágio. 
2) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.

IMPORTANTE:
Esse número pode ser informado através de qualquer entrada de sua preferência ou pode ser previamente definido no código;

Respo: 
num = int(input("Digite um número: "))  

fibonacci = [0, 1]
while fibonacci[-1] < num:
    next_num = fibonacci[-1] + fibonacci[-2]
    fibonacci.append(next_num)

if num in fibonacci:
    print(f"O número {num} pertence à sequência de Fibonacci!")
else:
    print(f"O número {num} não pertence à sequência de Fibonacci.")

3) Dado um vetor que guarda o valor de faturamento diário de uma distribuidora, faça um programa, na linguagem que desejar, que calcule e retorne:
• O menor valor de faturamento ocorrido em um dia do mês;
• O maior valor de faturamento ocorrido em um dia do mês;
• Número de dias no mês em que o valor de faturamento diário foi superior à média mensal.

IMPORTANTE:
a) Usar o json ou xml disponível como fonte dos dados do faturamento mensal;
b) Podem existir dias sem faturamento, como nos finais de semana e feriados. Estes dias devem ser ignorados no cálculo da média;

RESPOSTA: 

import statistics
faturamento_diario = [100.50, 250.80, 80.20, 300.00, 150.70, 0.00, 0.00, 200.90, 180.30, 90.10, 120.40, 210.60, 400.30, 280.90, 150.20, 90.00, 230.50, 170.20, 90.10, 300.40, 350.00, 190.50, 210.80, 270.70, 350.90, 400.20, 320.60, 280.40, 150.70, 100.00]

menor_valor = min(faturamento_diario)
maior_valor = max(faturamento_diario)
media_mensal = statistics.mean([valor for valor in faturamento_diario if valor != 0])
dias_acima_media = len([valor for valor in faturamento_diario if valor > media_mensal])

print(f"O menor valor de faturamento foi: R${menor_valor:.2f}")
print(f"O maior valor de faturamento foi: R${maior_valor:.2f}")
print(f"{dias_acima_media} dias tiveram faturamento diário superior à média mensal de R${media_mensal:.2f}.")

4) Dado o valor de faturamento mensal de uma distribuidora, detalhado por estado:

SP – R$67.836,43
RJ – R$36.678,66
MG – R$29.229,88
ES – R$27.165,48
Outros – R$19.849,53

Escreva um programa na linguagem que desejar onde calcule o percentual de representação que cada estado teve dentro do valor total mensal da distribuidora.

RESPOSTA: 

faturamento_mensal = {
    "SP": 67836.43,
    "RJ": 36678.66,
    "MG": 29229.88,
    "ES": 27165.48,
    "Outros": 19849.53
}

total_mensal = sum(faturamento_mensal.values())

for estado, faturamento in faturamento_mensal.items():
    percentual = (faturamento / total_mensal) * 100
    print(f"{estado}: {percentual:.2f}%")

5) Escreva um programa que inverta os caracteres de um string.

IMPORTANTE:
a) Essa string pode ser informada através de qualquer entrada de sua preferência ou pode ser previamente definida no código;
b) Evite usar funções prontas, como, por exemplo, reverse;

RESPOSTA: 

string = "exemplo de string"

string_invertida = ""
for i in range(len(string)-1, -1, -1):
    string_invertida += string[i]

print(string_invertida)
