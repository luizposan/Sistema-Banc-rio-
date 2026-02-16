# Sistema Bancário - Depósito, Saque e Extrato

saldo = 0
extrato = []

def depositar(valor):
    global saldo
    if valor > 0:
        saldo += valor
        extrato.append(f"Depósito: R$ {valor:.2f}")
        print("Depósito realizado com sucesso!")
    else:
        print("Valor inválido para depósito.")

def sacar(valor):
    global saldo
    if valor <= 0:
        print("Valor inválido para saque.")
    elif valor > saldo:
        print("Saldo insuficiente.")
    else:
        saldo -= valor
        extrato.append(f"Saque: R$ {valor:.2f}")
        print("Saque realizado com sucesso!")

def mostrar_extrato():
    print("\n=== EXTRATO ===")
    if extrato:
        for movimento in extrato:
            print(movimento)
    else:
        print("Não foram realizadas movimentações.")
    print(f"Saldo atual: R$ {saldo:.2f}")

# Menu principal
while True:
    print("\n=== MENU ===")
    print("1 - Depositar")
    print("2 - Sacar")
    print("3 - Extrato")
    print("4 - Sair")

    opcao = input("Escolha uma opção: ")

    if opcao == "1":
        valor = float(input("Informe o valor do depósito: "))
        depositar(valor)

    elif opcao == "2":
        valor = float(input("Informe o valor do saque: "))
        sacar(valor)

    elif opcao == "3":
        mostrar_extrato()

    elif opcao == "4":
        print("Encerrando sistema. Obrigado por utilizar nosso banco!")
        break

    else:
        print("Opção inválida. Tente novamente.")
     
