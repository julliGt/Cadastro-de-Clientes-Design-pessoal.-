# Definição da classe Cliente, que representa um cliente com nome, email e telefone
class Cliente:
    # Método construtor: é chamado quando criamos um novo Cliente
    def __init__(self, nome, email, telefone):
        self.nome = nome          # Armazena o nome do cliente
        self.email = email        # Armazena o email do cliente
        self.telefone = telefone  # Armazena o telefone do cliente

    # Método para mostrar os dados do cliente formatados
    def mostrar(self):
        print(f"Nome: {self.nome}")
        print(f"Email: {self.email}")
        print(f"Telefone: {self.telefone}")
        print("-------------------------")  # Linha separadora para visualização


# Função principal que controla o fluxo do programa
def main():
    clientes = []  # Lista para armazenar os objetos Cliente cadastrados

    while True:  # Loop infinito para mostrar o menu até o usuário escolher sair
        # Exibe as opções para o usuário
        print("\n1. Cadastrar cliente")
        print("2. Listar clientes")
        print("3. Sair")

        # Recebe a opção do usuário como string
        opcao = input("Escolha uma opção: ")

        # Se o usuário escolheu cadastrar cliente
        if opcao == '1':
            # Solicita dados do cliente
            nome = input("Nome: ")
            email = input("Email: ")
            telefone = input("Telefone: ")

            # Cria um novo objeto Cliente com os dados informados
            c = Cliente(nome, email, telefone)

            # Adiciona o cliente na lista
            clientes.append(c)

            print("Cliente cadastrado com sucesso!")

        # Se o usuário escolheu listar os clientes cadastrados
        elif opcao == '2':
            # Verifica se a lista está vazia
            if not clientes:
                print("Nenhum cliente cadastrado.")
            else:
                # Para cada cliente na lista, chama o método mostrar() para exibir dados
                for c in clientes:
                    c.mostrar()

        # Se o usuário escolheu sair do programa
        elif opcao == '3':
            print("Encerrando...")
            break  # Encerra o loop while e termina o programa

        else:
            # Caso o usuário digite uma opção inválida
            print("Opção inválida.")


# Ponto de entrada do programa
# Esse if garante que o main() só seja executado se o script for rodado diretamente
if __name__ == "__main__":
    main()
