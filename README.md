<h1>Programa para Stock</h1>
<p>
def adicionar_material(stock): (Esta função serve para guardar o código todo e sempre que o
quisermos usar é preciso apenas chamar a função, e esta função no caso guarda o código de
adicionar mais materiais ao stock)
nome = input("Nome do material: ") (esta função permite que insira o nome do material que
quer adicionar)
if nome in stock: (a função if significa o “se”, ou seja, se o nome que inseriu estiver no stock,
escreva...)
print("O material já existe no stock!") (esta função escreve na tela oque está dentro dela no
caso que o material já existe no stock)
else: (esta função quer dizer, senão, ou seja se(if)... senão(else)...)
quantidade = int(input(f"Quantidade a adicionar de {nome}: ")) (aqui tu podes escolher a
quantidade de um material anteriormente mensionado, que pretendes adicionar)
print(f"{nome} adicionado com sucesso!")

def consultar_stock(stock): (Esta função serve para guardar a parte de consulta ao stock)
nome = input("Nome do material para consulta: ")
if nome in stock:
print(f"O stock atual de {nome} é: {stock[nome]}")
else:
print(f"{nome} não encontrado no stock.")

def atualizar_stock(stock): (Esta função serve para guardar o código de atualizar o stock)
nome = input("Nome do material a atualizar: ")
if nome in stock:
operacao = input("Deseja adicionar (A) ou remover (R)? ").lower()
quantidade = int(input("Quantidade: "))
if operacao == "A":
stock[nome] += quantidade
print(f"{quantidade} unidade(s) adicionada(s) ao stock de {nome}.")
elif operacao == "R":
if quantidade <= stock[nome]:
stock[nome] -= quantidade
print(f"{quantidade} unidade(s) removida(s) do stock de {nome}.")
else:
print("Quantidade insuficiente em stock!")

def exibir_stock(stock): (Esta função serve para guardar o código todo e sempre que o
quisermos usar é preciso apenas chamar a função)
print("\nEstado Geral do Stock:")
print("Material\tQuantidade")

print("-" * 30)
for material, quantidade in stock.items(): (a função “.items()” serve para ler os items que
adicionaste a função)
print(f"{material}\t\t{quantidade}") (a função “\t” é um tabulador ou seja da [tab])

def main(): (Esta função guarda o código principal, das opções)
stock = {}
while True: (esta função permite a repetição do programa até que o utilizador o encerre)
print("\nGestão de Stock") (esta função “\n” serve para passar para a próxima linha com
espaço)
print("1. Adicionar Material")
print("2. Consultar Stock")
print("3. Atualizar Stock")
print("4. Exibir Stock Geral")
print("5. Sair")
opcao = input("Escolha uma opção: ")
if opcao == "1":
adicionar_material(stock)
elif opcao == "2":
consultar_stock(stock)
elif opcao == "3":
atualizar_stock(stock)
elif opcao == "4":
exibir_stock(stock)
elif opcao == "5":
print("Encerrando o programa...")
break (esta função faz com que o programa acabe, o break vem do inglês, de partir, ou
destruir ou seja acabar com alguma coisa, neste programa acaba com a repetição do mesmo)
else:
print("Opção inválida! Tente novamente.")
if __name__ == "__main__": (e esta função faz com que o código repita)
main()