def ler_arquivo(nome_arquivo):
    with open(nome_arquivo, 'r', encoding='utf-8') as arquivo:
        conteudo = arquivo.read()
        print("Conteúdo Original:")
        print(conteudo)
    return conteudo

def codificar_texto(nome_arquivo, conteudo):
    with open(nome_arquivo, 'w', encoding='utf-8') as arquivo:
        conteudo_codificado = conteudo.encode('utf-8').hex()
        arquivo.write(conteudo_codificado)
        print("Conteúdo Codificado:")
        print(conteudo_codificado)
    return conteudo_codificado

def decodificar_hexadecimal(conteudo_codificado):
    bytes_obj = bytes.fromhex(conteudo_codificado)
    conteudo_decodificado = bytes_obj.decode('utf-8')
    print("Conteúdo Decodificado:")
    print(conteudo_decodificado)

conteudo_original = ler_arquivo('teste.txt')
conteudo_codificado = codificar_texto('teste_codificado.txt', conteudo_original)
conteudo_decodificado = decodificar_hexadecimal(conteudo_codificado)
