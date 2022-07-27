# Automatiza-o-de-email-utilizando-python
Automatização de email utilizando python
import pyautogui
import pyperclip
import time

pyautogui.PAUSE = 1 

#Entrar no sistema
pyautogui.hotkey("ctrl","t") #Abrindo uma nova aba
pyperclip.copy("https://drive.google.com/drive/folders/149xknr9JvrlEnhNWO49zPcw0PW5icxga?usp=sharin")
pyautogui.hotkey("ctrl","v")#Colando link
pyautogui.press("enter")
time.sleep(5) #Tempo de carregamento
pyautogui.click(x=3413, y=455, clicks=2) #Encontar base de dados 
pyautogui.click(x=3428, y=552) #clicando no arquivo
pyautogui.click(x=4631, y=290) #clique nos 3 pontos  
pyautogui.click(x=4275, y=929) #fazendo download
time.sleep(7) #Tempo de carregamento em segundos 

import pandas as pd #importando dados de qualquer arquivo(pd - quer dizer a abreviação de pandas)
tabela = pd.read_excel(r"C:\Users\Iaaron Maciel\Desktop\Python com Lira\Vendas - Dez.xlsx") #Lendo uma base de dados em excel
display(tabela)

quantidade = tabela["Quantidade"].sum()
faturamento = tabela["Valor Final"].sum()
print(quantidade)
print(faturamento)

#Entrando no emial
pyautogui.hotkey("ctrl","t")
pyperclip.copy("https://mail.google.com/mail/u/0/#inbox")#copiando o emial
pyautogui.hotkey("ctrl","v") #Colando link
pyautogui.press("enter")
time.sleep(6)


pyautogui.click(x=3038, y=300) #Enviado o email
pyautogui.write("iaarongiordano@gmail.com") #Destinatátio(Para quem será enviado o email)
pyautogui.press("tab") #Selecionar o emial
pyautogui.press("tab") #Passar para o campo assunto
pyperclip.copy("Relatório de Vendas") 
pyautogui.hotkey("ctrl", "v")
pyautogui.press("tab") #Passando para o corpo do email

texto = f"""
Prezados, bom dia!!!

Segue como formalizado o relatório gerencial diário.
Saldo de Gusa: {quantidade}
Pátio de emergência: {faturamento}

Abs 
Iaaron Maciel
"""
pyperclip.copy(texto)
pyautogui.hotkey("ctrl", "v")


pyautogui.hotkey("ctrl", "enter")#Enviando o emial
