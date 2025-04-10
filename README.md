	  entrada = """
	
	[1] Depositar
	[2] Sacar
	[3] Extrato
	[4] Sair
	
	=> """
	
	saldo = 0 #saldo inicial deve ser 0
	limite = 500 #limite de 500 reais por saque
	extrato = ""
	numero_saques = 0
	LIMITE_SAQUES = 3
	
	while True:
	
	    escolha = input(entrada)
	
	    if escolha == "1":
	        valor = float(input("Valide seu valor do depósito: "))

        if valor > 0:
            valor
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f}\n"
            print (("Seu depósito de R${} foi realizado com sucesso!").format(valor))


        else:
            print("O valor informado não pode ser validado.")

    elif escolha == "2":
        saque = float(input("Qual o valor do saque?: "))

        excedeu_saldo = saque > saldo

        excedeu_limite = saque > limite

        excedeu_saques = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print("Saldo insuficiente.")

        elif excedeu_limite:
            print("Saque excedente.")

        elif excedeu_saques:
            print("Seus 3 saques diarios foram excedidos.")

        elif saque > 0:
            saque
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1
            print(("Saque de R${} foi realizado com sucesso!").format(saque))

        else:
            print("O valor informado é inválido.")

    elif escolha == "3":
        print("\n================ EXTRATO ================")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("==========================================")

    elif escolha == "4":
        break

    else:
        print("Favor valide novamente a operação desejada.")
